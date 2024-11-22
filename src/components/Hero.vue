<template>
  <div class="container-fluid text-primary-emphasis bg-primary-subtle mt-4 p-5">
    <div class="container">
      <div class="row align-items-center">
        <div class="col">
          <h1>Lorem ipsum dolor sit amet.</h1>
          <h5 class="text-secondary">
            Lorem ipsum dolor sit amet consectetur, adipisicing elit. Nisi,
            sunt?
          </h5>
        </div>
        <div class="col">
          <div id="carouselExample" class="carousel slide">
            
            <div class="carousel-inner" style="border-radius: 16px">
              <div v-for="(image, index) in images" :key="index" class="carousel-item" :class="{active: index == 0}">
                <img :src="image.download_url" class="d-block w-100" :alt="image.id" />
              </div>
            </div>

            <button
              class="carousel-control-prev"
              type="button"
              data-bs-target="#carouselExample"
              data-bs-slide="prev"
            >
              <span
                class="carousel-control-prev-icon"
                aria-hidden="true"
              ></span>
              <span class="visually-hidden">Previous</span>
            </button>
            <button
              class="carousel-control-next"
              type="button"
              data-bs-target="#carouselExample"
              data-bs-slide="next"
            >
              <span
                class="carousel-control-next-icon"
                aria-hidden="true"
              ></span>
              <span class="visually-hidden">Next</span>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import axios from "axios";

export default {
  data() {
    return {
      images: Array,
    };
  },
  mounted() {
    axios
      .get("https://picsum.photos/v2/list")
      .then((response) => (this.images = response.data.slice(0,3)));
  },
};
</script>
