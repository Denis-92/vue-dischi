<template>
  <div class="container flex flex-column" id="webapp-page">
    <componentHeader />
    <componentMain />
  </div>
</template>


<script>
import componentHeader from '@/components/componentHeader.vue';
import componentMain from '@/components/componentMain.vue';

export default {
  name: 'App',
  components: {
    componentHeader,
    componentMain,
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
