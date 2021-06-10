<template>
    <section class="container">
        <Nav @performSearch='searchGenre' />
        <div class="row">
            <div 
            v-for = '(album, index) in filteredAlbums'
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
import Nav from './Nav.vue';

import axios from 'axios';

export default {
    name: 'AlbumsContainer',
    components: {
        Album,
        Nav,
    },
    data: function () {
        return {
            apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
            albums: [],
            genreToSearch: '',
        }
    },
    computed: {
        filteredAlbums: function () {
            const newGenre = this.albums.filter(
                (element) => {
                    // console.log(element.genre);
                    return element.genre.includes(
                        this.genreToSearch
                    )
                }
            );
            return newGenre
        }
    },
    methods: {
        searchGenre: function (genreSelected) {
            console.log(genreSelected);
            this.genreToSearch = genreSelected;
            console.log(this.genreToSearch);
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