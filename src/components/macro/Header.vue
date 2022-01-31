<template>
    <header>
        <img src="../../assets/img/spotify_logo.png" alt="">        
    </header>
  
</template>

<script>
export default {
    name: 'Header',

}
</script>

<style lang="scss" scoped>
@import '../../assets/style/vars.scss';

header{
    background: $secondColor;
    padding: 5px 10px;

        img{
            height: 50px;
            width: 50px;
}
}

</style>