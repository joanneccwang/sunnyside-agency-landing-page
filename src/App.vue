<template>
  <div class="background"></div>
  <Header></Header>
  <ShowCase></ShowCase>
  <LearnMore v-for="section in learnMoreSections" :key="section.key"
    :sectionKey="section.key"
    :title="section.title"
    :paragraphs="section.paragraphs"
    :color="section.color"
    :image="section.image"
  ></LearnMore>
  <Photography></Photography>
  <Feedback></Feedback>
  <Gallery></Gallery>
  <Footer></Footer>
</template>

<script setup>
import { onMounted, provide, ref } from 'vue';

import Header from './components/Header.vue';
import ShowCase from './components/ShowCase.vue';
import LearnMore from './components/LearnMore.vue';
import Photography from './components/Photography.vue';
import Feedback from './components/Feedback.vue';
import Gallery from './components/Gallery.vue';
import Footer from './components/Footer.vue';

import MobileTransformBG from './assets/mobile/image-transform.jpg';
import MobileStandoutBG from './assets/mobile/image-stand-out.jpg';
const learnMoreSections = [{
    key: 'transform',
    title: 'Transform your brand',
    paragraphs: [
      'We are a full-service creative agency specializing in helping brands grow  fast.', 
      'Engage your clients through compelling visuals that do most of the   marketing for you.'],
    color: 'hsl(51, 100%, 49%)', // --yellow
    image: MobileTransformBG,
  }, {
    key: 'standout',
    title: 'Stand out to the right audience',
    paragraphs: ['Using a collaborative formula of designers, researchers,  photographers, videographers, and copywriters, we’ll build and extend your   brand in digital places.'],
    color: 'hsl(7, 99%, 70%)', // --soft-red:
    image: MobileStandoutBG,
  }];


/** Detect media query */
const isDesktop = ref(false);
provide('isDesktop', isDesktop);

const mediaQuery = window.matchMedia('(min-width: 768px)');
const handleMediaQueryChanged = (e) => {
  // Check if the media query is true
  isDesktop.value = e.matches;
};

onMounted(() => {
  // Register event listener
  mediaQuery.addListener(handleMediaQueryChanged);
  // Initial check
  handleMediaQueryChanged(mediaQuery);
});
</script>

<style>
@import './style/reset.css';
@import './style/variables.css';

.background {
  
  /* background: url('./assets/desktop-design.jpg') no-repeat;  */
  background: url('./assets/mobile-menu.jpg') no-repeat; 
  height: 6000px;
  width: 100%;
  position: absolute;
  top: 0;
  left: 0;
  opacity: 0.5;
  z-index: -1;
}
</style>
