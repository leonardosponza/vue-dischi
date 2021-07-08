<template>
  <section>
      <div class="row .bg-dark.bg-gradient">
          <div v-for="List in List" :key="List" class="col-5">

          </div>
      </div>
  </section>
</template>

<script>
import axios from 'axios';

export default {
    name:'List',
    data(){
        return{
            apiURL:'https://flynn.boolean.careers/exercises/api/array/music',
            List : []
        }
    },
    created(){
        this.getList();
    },
    methods:{
        getList(){
            axios
            .get(this.apiURL)
            .then(response => {
                this.List=response.data;
                console.log(this.List)
            })
            .catch(error=>{
                console.log('errore',error)
            })
        }
    }
}
</script>

<style>

</style>