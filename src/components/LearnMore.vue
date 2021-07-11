<template>
  <section id="learn-more" :class="[direction]">
    <img :src="image" alt="">
    <div class="info">
      <h1>{{ title }}</h1>
      <p v-for="(p, idx) in paragraphs" :key="`p-${idx}`">{{ p}}</p>
      <button ref="button">LEARN MORE</button>
    </div>
  </section>
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
    direction: {  // learn more block aligns left or right on desktop view
      type: String,
      required: true,
      default: 'left',  // left, right
    },
  },

  setup(props) {
    const { sectionKey, title, paragraphs, color, image, direction } = toRefs(props);
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
#learn-more {
  display: flex;
  flex-direction: column;
}
img {
  width: 100%;
  opacity: 0.5;
  /* height: 300px;
  width: 100%; */
}

.info {
  padding: 30px 25px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.info h1 {
  flex: 0 0 auto;
  margin: 25px 0px;
  line-height: 1.2em;
  color: var(--very-dark-desaturated-blue);
}
.info p {
  flex: 1;
  line-height: 1.6em;
  color: var(--very-dark-grayish-blue);
}
.info button {
  flex: 0 0 auto;
  font-family: 'Fraunces', sans-serif;
  margin: 35px 0px;
  font-size: 18px;
  border-bottom: 6px solid var(--yellow);
  cursor: pointer;
  color: var(--very-dark-desaturated-blue);
}

@media(min-width: 768px) {
  #learn-more {
    display: flex;
    flex-direction: row;
  }
  #learn-more.left {
    flex-direction: row-reverse;
  }

  img {
    flex: 0 0 50%;
    width: 50%;
    height: auto;
  }
  .info {
    flex: 0 0 50%;

    margin: auto;
    padding: 20px;
    padding-right: 60px;
    max-width: 530px;

    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    text-align: left;
  }
  #learn-more.left .info {
    padding: 20px;
    padding-left: 60px;
  }

  .info h1 {
    font-size: 42px;
  }
  .info button {
    margin: 40px 0px;
  }
}
</style>
