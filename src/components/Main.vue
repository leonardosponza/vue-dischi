<template>
  <section>
      <div  class=" pagina row row-cols-5  bg-secondary bg-gradient text-center">
          <div v-for="(song,index) in List" :key="index" class="col">              
              <Nome :details="song" />
          </div>
      </div>
  </section>
</template>

<script>
import axios from 'axios';
import Nome from './Nome.vue';

export default {
    name:'List',
    components:{
        Nome
    },
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
            .then(res => {
                console.log(res.data)
                this.List=res.data.response;
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
img{
    width: 150px;
    margin-top: 50px;
}
.pagina{
    height: 95vh;
}
</style>