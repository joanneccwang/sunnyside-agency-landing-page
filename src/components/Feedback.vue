<template>
  <section id="feedback">
    <h4 class="title">CLIENT TESTIMONIALS</h4>
    <div class="client-wrapper">
      <div v-for="feedback in feedbacks" :key="feedback.client"
        class="client">
        <img :src="feedback.photo" alt="">
        <p>{{ feedback.text }}</p>
        <h4>{{ feedback.client }}</h4>
        <span>{{ feedback.position }}</span>
      </div>
    </div>
  </section>
</template>
<script>
import EmilyPhoto from '../assets/image-emily.jpg';
import JenniePhoto from '../assets/image-jennie.jpg';
import ThomasPhoto from '../assets/image-thomas.jpg'; 

export default {
  setup() {
    const feedbacks = [{
      photo: EmilyPhoto,
      text: 'We put our trust in Sunnyside and they delivered, making sure our needs were met and deadlines were always hit.',
      client: 'Emily R.',
      position: 'Marketing Director',
    }, {
      photo: ThomasPhoto,
      text: 'Sunnyside’s enthusiasm coupled with their keen interest in our brand’s success made it a satisfying and enjoyable experience.',
      client: 'Thomas S.',
      position: 'Chief Operating Officer',
    }, {
      photo: JenniePhoto,
      text: 'Incredible end result! Our sales increased over 400% when we worked with Sunnyside. Highly recommended!',
      client: 'Jennie F.',
      position: 'Business Owner',
    }];

    return {
      feedbacks,
    };
  }, 
}
</script>
<style scoped>
#feedback {
  padding: 40px 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
#feedback .title {
  margin: 25px;
  letter-spacing: 2px;
  color: var(--grayish-blue);
}
#feedback .client-wrapper {
  display: flex;
  flex-direction: column;
}
#feedback .client {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 40px;
  color: var(--very-dark-desaturated-blue);
}
#feedback .client img {
  margin: 30px;
  border-radius: 50%;
  height: 75px;
  width: 75px;
}

#feedback .client p {
  text-align: center;
  margin: 10px;
  line-height: 1.6em;
  color: var(--very-dark-grayish-blue);
}

#feedback .client h4 {
  margin-top: 30px;
}

#feedback .client span {
  margin-top: 10px;
  font-size: 14px;
  color: var(--grayish-blue);
}

@media (min-width: 768px) {
  #feedback {
    margin: 100px 0px;
  }
  #feedback .title {
    letter-spacing: 2px;
    color: var(--grayish-blue);
    font-size: 25px;
    margin: 15px;
  }
  #feedback .client-wrapper {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    gap: 20px;
    margin: auto;
  }
  #feedback .client {
    max-width: 360px;
    margin-bottom: 25px;
  }
  #feedback .client img {
    margin: 60px;
  }
  #feedback .client p {
    margin: 0px;
    margin-bottom: 50px;
  }
}
</style>
