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
    display: flex;
    align-items: center;

        img{
            height: 50px;
            width: 50px;
            margin-right: 30px
        }
}

</style>