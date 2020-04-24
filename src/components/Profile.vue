<template>
  <div id="profile">
    <h3>{{ name }}</h3>
    <img :src="pictureUrl">
  </div>
</template>

<script>
export default {
  name: 'profile',
  props: ['name', 'pictureUrl']
}
</script>
<!-- styling for the component -->
<style>
  #profile {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
