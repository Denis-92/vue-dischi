<template>
    <div class="flex" id="header-area">
        <div id="logo-container">
            <img src="@/assets/img/logo-small.jpeg" alt="Logo Spotify">
        </div>
    </div>
</template>
  
<script>
export default {
    name: 'componentHeader',
}
</script>

<style lang="scss" scoped>
@import '@/assets/style/utilities.scss';
@import '@/assets/style/variables.scss';

#header-area {
    background-color: $header-bg-color;
}

#logo-container {
    height: 50px;
}

#logo-container>img {
    padding: 10px;
    height: 100%;
}
</style>  