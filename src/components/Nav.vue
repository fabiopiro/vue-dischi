<template>
  <nav>
      <img src="../assets/img/spotify.png" alt="logo">
      <select name="genre" id="genre" v-model="genreSelected" @change="$emit('performSearch' , genreSelected)">
          <option value="All">All Genre</option>
          <option value="Rock">Rock</option>
          <option value="Pop">Pop</option>
          <option value="Jazz">Jazz</option>
          <option value="Metal">Metal</option>
      </select>
  </nav>
</template>

<script>
export default {
    name: 'Nav',

    data: function () {
        return {
            genreSelected:'',
        }
    },

}
</script>

<style lang='scss' scoped>
  @import '../style/general.scss';

    nav {
        display: flex;
        justify-content: space-between;
        align-items: center;

        height: 75px;
        padding: 0 20px;
        background-color: $second-color;

        img {
            height: 50px;
            width: 50px;
        }
    }
</style>