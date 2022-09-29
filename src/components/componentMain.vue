<template>
    <div class="flex flex-grow flex-column flex-center-y" id="main-area">
        <div id="search-bar">
            <componentSearch :filterSearch="genres" @genreFiltered="selectedFilter" />
        </div>
        <div id="cards-container" class="flex flex-center-y flex-center-x flex-wrap">
            <div class="card flex flex-column flex-center-y" v-for="artist in showFilteredResult" :key="artist.poster">
                <div>
                    <img :src="artist.poster" alt="card" />
                </div>

                <div class="card-title"> {{ artist.title }} </div>

                <div>
                    <p>{{ artist.author }}</p>
                    <p>{{ artist.year }}</p>
                </div>
            </div>
        </div>
    </div>
</template>
  
<script>
import componentSearch from '@/components/componentSearch.vue';

export default {
    name: 'componentMain',
    data() {
        return {
            genreFiltered: '',
        }
    },
    props: {
        songs: Array,
    },
    components: {
        componentSearch,
    },
    computed: {
        genres() {
            const array = [];
            this.songs.forEach(song => {
                if (!array.includes(song.genre)) {
                    array.push(song.genre);
                }
            }
            );
            return array;
        },
        showFilteredResult() {
            const array = [];
            this.songs.forEach(song => {
                if (this.genreFiltered === song.genre || this.genreFiltered === "") {
                    array.push(song);
                }
            }
            );
            //return this.songs;
            return array;
        }
    },
    methods: {
        selectedFilter(genre) {
            this.genreFiltered = genre;
        },
    },
}
</script>

<style lang="scss" scoped>
@import '@/assets/style/utilities.scss';
@import '@/assets/style/variables.scss';

#main-area {
    background-color: $main-bg-color;
}

#cards-container {
    margin: 50px 200px;
}

.card {
    background-color: $cards-bg-color;
    color: $cards-text-color;
    width: calc(100% / 5 - 10px);
    margin: 5px;
    height: 48%;
}

.card>div {
    padding: 5px;
    text-align: center;
}

.card-title {
    color: white;
    text-transform: uppercase;
}
</style>  