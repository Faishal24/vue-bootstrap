<template>
  <div>
    <Navbar />
    <Hero />
    <Cards />
  </div>
</template>

<script>
import Cards from "./components/Cards.vue";
import Hero from "./components/Hero.vue";
import Navbar from "./components/Navbar.vue";

export default {
  components: {
    Navbar,
    Hero,
    Cards
  },
};
</script>
