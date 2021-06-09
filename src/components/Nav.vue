<template>
  <nav>
      <img src="../assets/img/spotify.png" alt="logo">
  </nav>
</template>

<script>
export default {
    name: 'Nav',
}
</script>

<style lang='scss' scoped>
    nav {
        display: flex;
        align-items: center;

        height: 75px;
        padding: 0 20px;
        background-color: black;

        img {
            height: 50px;
            width: 50px;
        }
    }
</style>