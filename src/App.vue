<template>
  <Componente />
</template>

<script>
import Componente from "./components/Componente.vue";

export default {
  name: "App",
  components: {
    Componente,
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

body{
  background-image: url(assets/cropped-RM_page-header_background1-3.png);
}

</style>
