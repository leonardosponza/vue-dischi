<template>
  <div>
      <h1>{{details.title}}</h1>
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