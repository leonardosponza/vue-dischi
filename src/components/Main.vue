<template>
  <section>
      <div class="row row-cols-5  bg-secondary bg-gradient w-auto p-3  ">
          <div v-for="(song,index) in List" :key="index" class="col">
              <img :src="song.poster" alt="">
              <nome :details="song" />
          </div>
      </div>
  </section>
</template>

<script>
import axios from 'axios';
import Nome from '@/components/main.vue'

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
}
</style>