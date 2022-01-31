<template>
  <div class="locandina text-center">
        <img :src="info.poster" alt="" class="img-fluid mb-3">
        <h4>{{info.title}}</h4>
        <h5 class="fs-6" >{{info.author}}</h5>
        <h6>{{info.year}}</h6>
    </div>
</template>

<script>
export default {
    name: 'Locandina',
        props: {
            info: Object
    }

}
</script>

<style lang="scss" scoped>
@import "../../assets/style/vars.scss";

.locandina{
    width: 18%;
    background-color: $secondColor;
    padding: 20px;
    margin-bottom: 20px;
    margin-right: 20px;

        h4{
            text-transform: uppercase;
            font-size: 17px;
            color: $firstColor;
            font-weight: bold;
            margin-bottom: 20px;
            }
        h5{
            font-weight: 400;
            color: grey;
            margin: 0;
        }

        h6{
            font-weight: 400;
            color: grey;
        }
}


</style>