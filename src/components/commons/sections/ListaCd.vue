<template>
  <section class="container">
      <div div v-if="!loading" class="row">
        <Locandina v-for="(locandina,index) in locandinaArray" :key="index" :info="locandina"
            class="col-2" />
        </div>
        <Loader v-else />
  </section>
</template>

<script>
import axios from "axios";
import Locandina from "../Locandina.vue";
import Loader from "../Loader.vue";

export default {
    name: 'ListaCd',
    data (){
        return{
            apiURL: "https://flynn.boolean.careers/exercises/api/array/music",
            locandinaArray: [],
            loading: true
        }
    },
    components: {
        Locandina,
        Loader
    },
    created(){
        this.getLocandina();
    },
    methods: {
        getLocandina(){
            axios
                .get(this.apiURL)
                .then( (risposta) => {
                    // handle success
                    this.locandinaArray = risposta.data.response;
                    this.loading = false;
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                });
        }
    }

}
</script>

<style lang="scss" scoped>

.container{
    width: 80%;
}

</style>