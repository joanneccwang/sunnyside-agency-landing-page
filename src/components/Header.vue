<template>
  <header>
    <img src="../assets/logo.svg" alt="">
    <img class="menu" src="../assets/icon-hamburger.svg" alt="">
  </header>
</template>

<script>
export default {
  
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
  justify-content: space-between;
}

.menu {
  cursor: pointer;
}
</style>

