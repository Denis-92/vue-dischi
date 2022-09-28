<template>
    <div class="flex flex-grow" id="main-area">
        <div id="cards-container" class="flex flex-center-y flex-center-x flex-wrap">
            <div class="card flex flex-column flex-center-y" v-for="artist in songs" :key="artist.poster">
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
    height: 50%;
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