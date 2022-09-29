<template>
    <div>
        <select v-model="receiveInput" @change="filteredContent">
            <option value="">No Genre Filter</option>
            <option :value="genre" v-for="genre in filterSearch" :key="genre"> {{ genre }} </option>
        </select>
    </div>
</template>
  
<script>
export default {
    name: 'componentSearch',
    props: {
        filterSearch: Array
    },
    data() {
        return {
            receiveInput: ""
        }
    },
    methods: {
        filteredContent() {
            this.$emit('genreFiltered', this.receiveInput);
        }
    },
}
</script>

<style lang="scss" scoped>
@import '@/assets/style/utilities.scss';
</style>  