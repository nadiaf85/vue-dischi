<template>
  <main class="container-fluid">
        <div class="row">
            <div class="col">
                <ListaCd/>
            </div>
        </div>
    </main>
</template>

<script>
import ListaCd from "../commons/sections/ListaCd.vue"

export default {
    name: 'Main',
    components: {
        ListaCd
    }

}
</script>

<style lang="scss" scoped>

main{
    background-color: #1e2d3b;
    padding: 60px;
    min-height: calc(100vh - 60px)
}

</style>