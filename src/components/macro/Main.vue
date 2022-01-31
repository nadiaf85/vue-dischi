<template>
  <main class="container">
        <div class="row">
            <div class="col">
                <ListaCd/>
            </div>
        </div>
    </main>
</template>

<script>
import ListaCd from "../sections/ListaCd.vue"

export default {
    name: 'Main',
    components: {
        ListaCd
    }

}
</script>

<style lang="scss" scoped>

</style>