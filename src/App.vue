<template>
  <div class="container flex flex-column" id="webapp-page">
    <componentHeader />
    <componentMain />
  </div>
</template>


<script>
import componentHeader from '@/components/componentHeader.vue';
import componentMain from '@/components/componentMain.vue';
import axios from 'axios';

export default {
  name: 'App',
  data() {
    return {
      artists: []
    }
  },
  components: {
    componentHeader,
    componentMain,
  },
  created() {
    console.log('axios collegamento');
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then(
      ({ status, data }) => {
        if (status === 200) {
          this.artists = data;
        }
      }
    );
  },
}
</script>


<style lang="scss">
@import '@/assets/style/generics.scss';
@import '@/assets/style/utilities.scss';

#webapp-page {
  height: 100vh;
}
</style>
