<template>
    <div>
        <select v-model="receiveInput">
            <option v-for="genre in filterSearch" :key="genre"> {{ genre }} </option>
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
}
</script>

<style lang="scss" scoped>
@import '@/assets/style/utilities.scss';
</style>  