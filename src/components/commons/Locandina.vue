<template>
  <div class="locandina text-center">
        <img :src="info.poster" alt="" class="img-fluid mb-3">
        <h4>{{info.author}}</h4>
        <div>{{info.year}}</div>
    </div>
</template>

<script>
export default {
    name: Locandina,
        props: {
            info: Object
    }

}
</script>

<style>

</style>