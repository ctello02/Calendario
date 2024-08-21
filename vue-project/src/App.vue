<script setup>
import { RouterView } from 'vue-router'
import NavBar from './components/NavBar.vue'
</script>

<template>
  <NavBar />
  <div class="content">
    <RouterView />
  </div>
</template>

<style>
html,
body,
#app {
  margin: 0;
  padding: 0;
  height: 100%;
}

.content {
  padding-top: 50px;
  /* Altura de la barra de navegación */
  height: calc(100% - 50px);
  /* Resta la altura de la barra de navegación */
  box-sizing: border-box;
  display: flex;
  justify-content: center;
  align-items: center;
  padding-left: 20px;
  padding-right: 20px;
  max-width: 800px;
  margin: 0 auto;
  text-align: center;
}
</style>
