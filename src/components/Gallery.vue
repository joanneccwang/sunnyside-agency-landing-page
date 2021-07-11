<template>
  <section id="gallery">
    <img v-for="image in images" :src="image" alt="">
  </section>
</template>
<script>
import MilkMobile from '../assets/mobile/image-gallery-milkbottles.jpg';
import OrangeMobile from '../assets/mobile/image-gallery-orange.jpg';
import ConeMobile from '../assets/mobile/image-gallery-cone.jpg';
import SugarMobile from '../assets/mobile/image-gallery-sugar-cubes.jpg';
export default {
  setup() {
    const images = [MilkMobile, OrangeMobile, ConeMobile, SugarMobile];
    return {
      images,
    };
  },
}
</script>
<style scoped>
#gallery {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}
#gallery img {
  flex: 0 0 50%;
  min-width: 50%;
}
</style>
