<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import Header from './components/Home/Header.vue';
import Footer from './components/Home/Footer.vue';
</script>

<template>
  
    

    <div class="wrapper">
    <Header></Header>
    </div>
   

  <RouterView />
  <Footer></Footer>
</template>

<style scoped>

</style>
