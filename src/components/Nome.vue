<template>
  <div>
      <img :src="details.poster" alt="">
      <h3>{{details.title}}</h3>
      <div>{{details.author}}</div>
      <div>{{details.year}}</div>
  </div>
</template>

<script>
export default {
    name:'autori',
    props:["details"]
}
</script>

<style>

</style>