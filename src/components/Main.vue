<template>
  <section>
      <div class="row row-cols-2  bg-info bg-gradient w-auto p-3  ">
          <div v-for="(song,index) in List" :key="index" class="col">
              {{ index.title }} 
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
            List : ''
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
                console.log(response.data)
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