<template>
  <section class="container">
      <div v-if="!loading" class="row">
        <Locandina v-for="locandina in locandinaArray" :key="locandina.id" :info="locandina"
            class="col-12 col-sm-6 col-lg-3" />
        </div>
  </section>
</template>

<script>
import axios from "axios";
import Locandina from "../commons/Locandina.vue";

export default {
    name: ListaCd,
    data (){
        return{
            apiURL: "https://flynn.boolean.careers/exercises/api/array/music",
            locandinaArray: []
        }
    },
    components: {
        Locandina,
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
                    // this.loading = false;
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                });
        }
    }

}
</script>

<style>

</style>