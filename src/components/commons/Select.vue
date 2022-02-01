<template>
  <select name="genere" 
        v-model="genereSelezionato" @change="$emit('filtra', genereSelezionato)" >
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
    </select>
</template>

<script>
export default {
    name: "Select",
    data (){
        return{
            genereSelezionato: "",
        }
    },
}
</script>

<style lang="scss" scoped>

select{
    margin-left: 20px;
    width: 10%;
}

</style>