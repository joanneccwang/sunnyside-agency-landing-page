<template>
  <section id="gallery">
    <img v-for="image in images" :src="image" alt="">
  </section>
</template>
<script>
import { inject, computed } from 'vue';
import MilkMobile from '../assets/mobile/image-gallery-milkbottles.jpg';
import OrangeMobile from '../assets/mobile/image-gallery-orange.jpg';
import ConeMobile from '../assets/mobile/image-gallery-cone.jpg';
import SugarMobile from '../assets/mobile/image-gallery-sugar-cubes.jpg';

import MilkDesktop from '../assets/desktop/image-gallery-milkbottles.jpg';
import OrangeDesktop from '../assets/desktop/image-gallery-orange.jpg';
import ConeDesktop from '../assets/desktop/image-gallery-cone.jpg';
import SugarDesktop from '../assets/desktop/image-gallery-sugarcubes.jpg';

export default {
  setup() {
    const isDesktop = inject('isDesktop');

    const images = computed(() => {
      return isDesktop.value
        ? [MilkDesktop, OrangeDesktop, ConeDesktop, SugarDesktop]
        : [MilkMobile, OrangeMobile, ConeMobile, SugarMobile];
    });

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
  max-width: 50%;
}

@media (min-width: 768px) {
  #gallery img {
    flex: 1;
    max-width: 25%;
  }
}
</style>
