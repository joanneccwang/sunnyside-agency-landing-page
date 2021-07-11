<template>
  <img :src="image" alt="">
  <div class="learn-more">
    <h1>{{ title }}</h1>
    <p v-for="(p, idx) in paragraphs" :key="`p-${idx}`">{{ p}}</p>
    <button ref="button">LEARN MORE</button>
  </div>
</template>
<script>
import { toRefs, ref, onMounted } from 'vue';
export default {
  props: {
    sectionKey: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    paragraphs: {
      type: Array,
      required: true,
    },
    color: {
      type: String,
      required: true,
      default: 'yellow',
    },
    image: {  // path to mobile image
      type: String,
      required: true,
    },
  },

  setup(props) {
    const { sectionKey, title, paragraphs, color, image } = toRefs(props);
    const button = ref(null);

    onMounted(() => {
      button.value.style.borderColor = color.value;
    });

    return {
      button,
    };
  },
};

</script>
<style scoped>
img {
  width: 100%;
  /* opacity: 0.5; */
  /* height: 300px;
  width: 100%; */
}

.learn-more {
  padding: 30px 25px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.learn-more h1 {
  flex: 0 0 auto;
  margin: 25px 0px;
  line-height: 1.2em;
  color: var(--very-dark-desaturated-blue);
}
.learn-more p {
  flex: 1;
  line-height: 1.6em;
  color: var(--very-dark-grayish-blue);
}
.learn-more button {
  flex: 0 0 auto;
  font-family: 'Fraunces', sans-serif;
  margin: 35px 0px;
  font-size: 18px;
  border-bottom: 6px solid var(--yellow);
  cursor: pointer;
  color: var(--very-dark-desaturated-blue);
}
</style>
