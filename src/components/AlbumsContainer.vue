<template>
    <section class="container">
        <div class="row">
            <div 
            v-for = '(album, index) in albums'
            :key = 'index'
            class="col-6 col-md-4 col-lg-3">
                <Album 
                :item='album'
                />
            </div>

        </div>
        
    </section>
</template>

<script>
import Album from './Album.vue';
import axios from 'axios';

export default {
    name: 'AlbumsContainer',
    components: {
        Album,
    },
    data: function () {
        return {
            apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
            albums: [],
        }
    },
    created: function () {
        axios
            .get(this.apiUrl)
            .then(
                (call) => {

                    this.albums = call.data.response;

                }
            )
            .catch();
    }
    
}
</script>

<style lang='scss' scoped>

</style>