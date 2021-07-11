<template>
  <header>
    <img class="logo" src="../assets/logo.svg" alt="">
    <img v-if="!isDesktop" class="menu" src="../assets/icon-hamburger.svg" alt="" @click="toggleNav">
    <ul v-if="isDesktop || showNav" class="nav">
      <li>About</li>
      <li>Service</li>
      <li>Projects</li>
      <li class="contact">CONTACT</li>
    </ul>
  </header>
</template>

<script>
import { inject, ref } from 'vue';
export default {
  setup() {
    const isDesktop = inject('isDesktop');
    const showNav = ref(false);

    const toggleNav = () => {
      showNav.value = !showNav.value;
    };
    return {
      isDesktop,

      // nav control
      showNav,
      toggleNav,
    };
  },
}
</script>
<style scoped>
header {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1;

  margin: 32px 24px;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
}
.menu {
  cursor: pointer;
}
.nav {
  position: absolute;
  top: 75px;
  width: 100%;
  background: var(--white);
  display: flex;
  flex-direction: column;
  align-items: center;
  color: black;
  padding: 30px 0px;
}
.nav::before {
  content: '';
  position: absolute;
  top: -25px;
  right: 0px;
  height: 0px;
  border: 25px solid white;
  border-top: 25px solid transparent;
  border-left: 25px solid transparent;
}
.nav li {
  padding: 15px 25px;
  font-size: 20px;
  cursor: pointer;
}
.nav li.contact {
  margin: 20px 0px 10px 0px;
  color: black;
  border-radius: 35px;
  background-color: var(--yellow); 
  font-family: 'Fraunces', sans-serif;
  font-size: 16px;
}
.nav li.contact:hover {
  color: var(--white);
  background-color: rgba(255,255,255, 0.2); 
}


@media(min-width: 768px) {
  header {
    margin: 35px;
  }
  .logo {
    height: 34px;
  }
  .nav {
    position: static;
    background: unset;
    display: flex;
    flex-direction: row;
    justify-content: flex-end;
    color: var(--white);
    padding: 0px;
  }
  .nav::before {
    display: none;
  }
  .nav li {
    padding: 15px 20px;
    margin: 0 8px;
  }
  .nav li.contact {
    margin: 0px 15px;
    padding: 15px 30px;
    color: black;
    border-radius: 35px;
    background-color: var(--white); 
    font-family: 'Fraunces', sans-serif;
  }
  .nav li.contact:hover {
    color: var(--white);
    background-color: rgba(255,255,255, 0.2); 
  }
}
</style>

