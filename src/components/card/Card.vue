<script setup>
import { ref } from 'vue';
import { useCityStore } from '@/stores/cityStore';

const cityStore = useCityStore();
const cities = cityStore.cities;



</script>
<template>
  <div class="cities">
    <div class="cities-cards">
      <div v-for="(city, index) in cities" :key="index" class="city-card">
        <img :src="city.image" :alt="city.title" @click="toggleDescription(index)">
           <h3>{{ city.title }}</h3>
           <p> {{ city.description }}</p>
           <button type="button" class="btn btn-outline-dark">More</button>
            
      </div>
    </div>
  </div>
</template>



<style scoped lang="scss">
.cities-cards {
  display: grid;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  margin-bottom: 5rem;


.city-card {
  margin: 1rem;
  padding: 1rem;
  border: 1px solid #ccc;
  border-radius: 0.5rem;
  text-align: center;
}

.city-card img {
  width: 100%;
  max-width: 90px;
  cursor: pointer;
}

h5, h6 {
  font-size: small;
}}
</style>
