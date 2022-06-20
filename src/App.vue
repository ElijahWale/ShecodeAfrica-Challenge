<template>
  <div class="container">
    <Nav/>
    <router-view/>
  </div>
</template>
<script>
import Nav from '@/components/Nav';
export default {
  components: {
    Nav
  },
}
</script>

<style>
*{
  margin: 0;
  padding:0;
  box-sizing: border-box;
}
#app{
    font-family: 'Poppins', sans-serif;
}
nav a.router-link-exact-active {
  color: #42b983;
}
.container{
  width: 90%;
  max-width: 1200px;
  margin: 0 auto;
  border: 1px solid #fff;
}
</style>
