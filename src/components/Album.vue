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

        margin: 15px 0px;
        padding: 10px;
        background-color: $second-color;

        img {
            width: 100%;
            height: 50%;
            margin-bottom: 30px;
            object-fit: contain;
        }

        .title {
            text-transform: uppercase;
            font-weight: bold;
            font-size: 25px;
            color: white;
        }

        .author,
        .year {
            color: gray;
        }
    }
</style>