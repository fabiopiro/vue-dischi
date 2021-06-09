<template>
  <div class="album">
      <img :src="item.poster" alt="item.title">
      <p class="title"> {{ item.title }} </p>
      <p class="author"> {{ item.author }} </p>
      <p class="year"> {{ item.year }} </p>
      
  </div>
</template>

<script>
export default {
    name: 'Album',
    props: [ 'item' ]

}
</script>

<style lang='scss' scoped>
  @import '../style/general.scss';

    .album {
        text-align: center;

        padding: 10px;
        margin: 10px;
        height: 300px;
        background-color: $second-color;

        img {
            width: 100%;
            height: 50%;
            margin-bottom: 15px;
            object-fit: contain;
        }

        .title {
            text-transform: uppercase;
            color: white;
        }

        .author,
        .year {
            color: lightgray;
        }
    }
</style>