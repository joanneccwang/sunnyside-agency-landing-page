<template>
  <section id="photography">
    <div v-for="photo in photos" :key="photo.title"
      class="photo"
      :style="{backgroundImage: `url(${photo.background})`, opacity: 0.5}">
      <h1 :style="{ color: `var(--${photo.color})`}">{{ photo.title }}</h1>
      <p :style="{ color: `var(--${photo.color})`}">{{ photo.paragraph }}</p>
    </div>
  </section>
</template>
<script>
import { inject } from 'vue';

import MobileGraphicBG from '../assets/mobile/image-graphic-design.jpg';
import MobilePhotographyBG from '../assets/mobile/image-photography.jpg';
import DesktopGraphicBG from '../assets/desktop/image-graphic-design.jpg';
import DesktopPhotographyBG from '../assets/desktop/image-photography.jpg';

export default {
  setup() {
    const isDesktop = inject('isDesktop');

    const photos = [{
      title: 'Graphic Design',
      paragraph: 'Great design makes you memorable. We deliver artwork that underscores your brand message and captures potential clients’ attention.',
      background: isDesktop ? DesktopGraphicBG : MobileGraphicBG,
      color: 'dark-desaturated-cyan',
    }, {
      title: ' Photography',
      paragraph: 'Increase your credibility by getting the most stunning, high-quality photos that improve your business image.',
      background: isDesktop ? DesktopPhotographyBG : MobilePhotographyBG,
      color: 'dark-blue',
    }];


    return {
      photos,
    };
  },
}
</script>
<style scoped>
#photography {
  display: flex;
  flex-direction: column;
}
.photo {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-end;
  padding: 30px;
  height: 600px;
  background-position: center;
  background-size: cover;
}
.photo h1 {
  flex: 0 0 auto;
  margin: 25px 0px;
  line-height: 1.2em;
}
.photo p {
  text-align: center;
  flex: 0 0 auto;
  line-height: 1.6em;
}

@media (min-width: 768px) {
  #photography {
    display: flex;
    flex-direction: row;
    background-position: center;
    background-repeat: no-repeat;
  }
  .photo {
    flex: 0 0 50%;
    max-width: 50%;
    padding: 0px;
  }
  .photo p {
    max-width: 380px;
    margin-bottom: 60px;
    padding: 0px 20px;
  }
}
</style>
