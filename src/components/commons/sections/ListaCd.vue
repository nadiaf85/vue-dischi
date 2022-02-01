<template>
  <section class="container">
      <div div v-if="!loading" class="row">
        <div class="genere">Scegli un genere <Select @filtra="getGenere"/></div>
        <Locandina v-for="(locandina,index) in cdFiltrati" :key="index" :info="locandina"
            class="col-2" />
        </div>
        <Loader v-else />
  </section>
</template>

<script>
import axios from "axios";
import Locandina from "../Locandina.vue";
import Loader from "../Loader.vue";
import Select from "../Select.vue";


export default {
    name: 'ListaCd',
    data (){
        return{
            apiURL: "https://flynn.boolean.careers/exercises/api/array/music",
            locandinaArray: [],
            loading: true,
            genereSelezionato: ""
        }
    },
    components: {
        Locandina,
        Loader,
        Select
    },
    created(){
        this.getLocandina();
    },
    computed:{
        cdFiltrati(){
            return this.locandinaArray.filter((locandina) =>{
                return locandina.genre.includes(this.genereSelezionato)
            });
        }
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
        },
        getGenere(genere)
        {
            this.genereSelezionato = genere;
            console.log(this.genereSelezionato);
        }
    }

}
</script>

<style lang="scss" scoped>

.container{
    width: 80%;
}

.genere{
    display: flex;
    justify-content: center;
    margin-bottom: 20px;
}

</style>