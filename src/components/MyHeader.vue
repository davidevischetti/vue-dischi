<!-- HTML -->
<template>
  <header>
    <img src="../assets/img/spotify-logo.png" alt="spotify-logo">
  </header>
</template>

<!-- JS -->
<script>
export default {
  name: 'MyHeader',
}
</script>

<!-- CSS -->
<style scoped lang="scss">

  header {
    height: 50px;
    width: 100%;
    background-color: #2e3a46;
    position: fixed;
    top: 0;
    left: 0;

    img {
      height: 100%;
    }
  }

</style>
