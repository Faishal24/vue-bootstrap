<template>
  <div class="mt-5 mx-5">
    <div class="row justify-content-center">
      <div
        v-for="(image, index) in images"
        class="col-4"
        style="width: 18rem"
      >
        <div :key="index"
        class="card">
          <img :src="image.download_url" class="card-img-top" alt="..." />
          <div class="card-body">
            <h5 class="card-title">Card title</h5>
            <p class="card-text">
              Some quick example text to build on the card title and make up the
              bulk of the card's content.
            </p>
            <a href="#" class="btn btn-primary">Go somewhere</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import axios from "axios";
import { onMounted, ref } from "vue";

export default {
  setup() {
    const images = ref([]);

    onMounted(() => {
      axios
        .get("https://picsum.photos/v2/list?page=12")
        .then((response) => (images.value = response.data.slice(0, 10)))
        .catch((error) => console.log(error));
    });

    return { images };
  },
};
</script>
