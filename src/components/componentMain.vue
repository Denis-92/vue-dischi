<template>
    <div class="flex flex-grow" id="main-area">
        <div id="cards-container" class="flex flex-center-y flex-center-x flex-wrap">
            <div class="card flex flex-column flex-center-y" v-for="artist in songs" :key="artist.poster">
                <div>
                    <img src="@/assets/img/logo-small.jpeg" alt="card" />
                </div>

                <div class="card-title"> {{ songs.title }} </div>

                <div>ARTIST</div>
            </div>
        </div>
    </div>
</template>
  
<script>
export default {
    name: 'componentMain',
    props: {
        songs: Array
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
    height: 40%;
}

.card>div {
    padding: 5px;
}

.card-title {
    color: white;
}
</style>  