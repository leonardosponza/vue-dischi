<template>
  <section>
      <div class="row .bg-dark.bg-gradient">
          <div class="col-5">

          </div>
      </div>
  </section>
</template>

<script>
import axios from 'axios';

export default {
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
            .then(res => {
                console.log(res.data);
            })
        }
    }
}
</script>

<style>

</style>