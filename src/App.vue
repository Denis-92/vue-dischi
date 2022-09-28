<template>
  <div class="container flex flex-column" id="webapp-page">
    <componentHeader />
    <componentMain :songs="songs" />
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
      urlMusic: 'https://flynn.boolean.careers/exercises/api/array/music',
      songs: []
    }
  },
  components: {
    componentHeader,
    componentMain,
  },
  created() {
    axios.get(this.urlMusic).then(
      ({ status, data }) => {
        if (status === 200) {
          this.songs = data.response;
          console.log(this.artists);
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
