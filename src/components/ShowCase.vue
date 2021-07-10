<template>
  <section id="showcase">
    <div class="title">WE ARE CREATIVES</div>
    <img src="../assets/icon-arrow-down.svg" alt="">
  </section>
</template>
<script>
export default {
  
}
</script>
<style scoped>
#showcase {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;

  height: 540px;
  background: url('../assets/mobile/image-header.jpg') no-repeat center/cover;
  /* opacity: 0.5; */
}

#showcase > .title {
  color: var(--white);
  font-family: 'Fraunces', sans-serif;
  font-weight: 900;
  font-size: 40px;
  letter-spacing: 6px;
  line-height: 50px;
  margin: 40px 0px 25px 0px;
  /* margin: 30px; */
}

#showcase > img {
  margin: 25px 0px 30px 0px;
  /* margin: 30px; */
}
</style>

