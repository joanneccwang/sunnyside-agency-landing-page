<template>
  <section v-for="photo in photos" :key="photo.title"
    class="photography"
    :style="{background: `url(${photo.background}) center/cover`, height: '600px'}"
  >  
    <h1 :style="{ color: `var(--${photo.color})`}">{{ photo.title }}</h1>
    <p :style="{ color: `var(--${photo.color})`}">{{ photo.paragraph }}</p>
  </section>
</template>
<script>
import GraphicBG from '../assets/mobile/image-graphic-design.jpg';
import PhotographyBG from '../assets/mobile/image-photography.jpg';
export default {
  setup() {
    const photos = [{
      title: 'Graphic Design',
      paragraph: 'Great design makes you memorable. We deliver artwork that underscores your brand message and captures potential clients’ attention.',
      background: GraphicBG,
      color: 'dark-desaturated-cyan',
    }, {
      title: ' Photography',
      paragraph: 'Increase your credibility by getting the most stunning, high-quality photos that improve your business image.',
      background: PhotographyBG,
      color: 'dark-blue',
    }];

    return {
      photos,
    };
  },
}
</script>
<style scoped>
section {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-end;
  padding: 30px;
}
.photography h1 {
  flex: 0 0 auto;
  margin: 25px 0px;
  line-height: 1.2em;
}
.photography p {
  text-align: center;
  flex: 0 0 auto;
  line-height: 1.6em;
}
</style>
