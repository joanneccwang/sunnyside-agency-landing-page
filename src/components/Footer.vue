<template>
  <section id="footer">
    <span class="logo">sunnyside</span>
    <div class="btn-wrapper">
      <button class="btn" v-for="btn in buttons" :key="btn.text">
        {{ btn.text }}
      </button>
    </div>
    <div class="icon-wrapper">
      <img v-for="social in socials" :key="social.key"
      :src="social.icon" alt="">
    </div>
  </section>
</template>
<script>
import FBIcon from '../assets/icon-facebook.svg';
import InstaIcon from '../assets/icon-instagram.svg';
import TwitterIcon from '../assets/icon-twitter.svg';
import PinterestIcon from '../assets/icon-pinterest.svg';

export default {
  setup() {
    const buttons = [{
      text: 'About',
    }, {
      text: 'Service',
    }, {
      text: 'Projects',
    }];

    const socials = [{
      key: 'facebook',
      icon: FBIcon,
    }, {
      key: 'instagram',
      icon: InstaIcon,
    }, {
      key: 'twitter',
      icon: TwitterIcon,
    }, {
      key: 'pinterest',
      icon: PinterestIcon,
    }];
    return {
      buttons,
      socials,
    };
  },
}
</script>
<style scoped>
#footer {
  display: flex;
  flex-direction: column;
  align-items: stretch;
  padding: 40px;
  background-color: hsl(167, 44%, 70%);
}

#footer .logo {
  color: var(--dark-moderate-cyan);
  font-family: 'Fraunces', sans-serif;
  font-weight: 900;
  font-size: 35px;
  text-align: center;
  letter-spacing: 0px;
}

#footer .btn-wrapper {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  margin: 40px 0px;
  color: var(--dark-moderate-cyan);
}

#footer .btn-wrapper .btn {
  cursor: pointer;
}
#footer .btn-wrapper .btn:hover {
  color: var(--white);
}

#footer .icon-wrapper {
  margin: 50px;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}
#footer .icon-wrapper img {
  margin: 0px 15px;
  cursor: pointer;
}

#footer .icon-wrapper img:hover {
  filter: brightness(0) invert(1);
}
</style>
