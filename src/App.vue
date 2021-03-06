<template>
  <Header></Header>
  <ShowCase></ShowCase>
  <LearnMore v-for="section in learnMoreSections" :key="section.key"
    :sectionKey="section.key"
    :title="section.title"
    :paragraphs="section.paragraphs"
    :color="section.color"
    :image="section.image"
    :direction="section.direction"
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
import DesktopTransformBG from './assets/desktop/image-transform.jpg';
import DesktopStandoutBG from './assets/desktop/image-stand-out.jpg';


/** Detect media query */
const isDesktop = ref(false);
provide('isDesktop', isDesktop);

const mediaQuery = window.matchMedia('(min-width: 768px)');
const handleMediaQueryChanged = (e) => {
  // Check if the media query is true
  isDesktop.value = e.matches;
};

const learnMoreSections = [{
    key: 'transform',
    title: 'Transform your brand',
    paragraphs: [
      'We are a full-service creative agency specializing in helping brands grow fast. Engage your clients through compelling visuals that do most of the   marketing for you.'],
    color: 'hsl(51, 100%, 49%)', // --yellow
    image: isDesktop ? DesktopTransformBG : MobileTransformBG,
    direction: 'left',
  }, {
    key: 'standout',
    title: 'Stand out to the right audience',
    paragraphs: ['Using a collaborative formula of designers, researchers,  photographers, videographers, and copywriters, we’ll build and extend your   brand in digital places.'],
    color: 'hsl(7, 99%, 70%)', // --soft-red:
    image: isDesktop ? DesktopStandoutBG : MobileStandoutBG,
    direction: 'right',
  }];

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
</style>
