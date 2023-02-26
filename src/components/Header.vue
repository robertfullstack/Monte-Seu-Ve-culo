<template>
  <div id="menu"> 
    <nav>
    <router-link to="">
        <img :src="logo" :alt="alt" id="header-logo">
    </router-link>
    <router-link to="/">Home</router-link> |
    <router-link to="/pedidos">Pedidos</router-link> |
    <router-link to="/produtos">Produtos</router-link>
  </nav>
  </div>
</template>


<script>
    export default {
        name: "Header",
        props: ["logo", "alt"]
    }

</script>


<style scoped>



  #header-logo {
      width: 100px;
  }

  #menu nav {
      color: white;
      display: flex;
      justify-content: space-evenly;
      align-items: center;
  }
  
  #menu nav a {
    color: #00ff84;
    text-decoration: none;
    transition: .2s;
  }
  
  #menu nav a:hover {
    color: white;
  }
</style>