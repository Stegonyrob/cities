<script setup>
import { ref } from 'vue';
import { useCityStore } from '@/stores/cityStore';



const cityStore = useCityStore();
const cities = computed(() => cityStore.state.cities);



</script>
<template>

<nav id="sidebarMenu" class=" d-sm-block sidebar w-25  bg-white">
    <div class="position-sticky">
      <div class="list-group list-group-flush mx-3 mt-4">
          
                <ul  class="list-group-item list-group-item-action py-2 ripple">
                <li>
                    <div v-for="(city, index) in cities" :key="index" class="city-card">
                        <img :src="city.image" :alt="city.title" @click="toggleDescription(index)">
                        <h6>{{ city.title }}</h6>
                    </div>
                </li>
            </ul>
        </div>
    </div>
    <nav aria-label="page" class="page">
      <ul class="pagination active pagination-lg justify-content-center" aria-current="page">
        <li class="page-item" :class="{ disabled: currentPage === 1 }">
          <button class="page-link" @click="changePage(currentPage - 1)" :disabled="currentPage === 1"><i
              class="bi bi-arrow-left"></i></button>
        </li>
        <li class="page-item" v-for="page in pages" :key="page">
          <button class="page-link" @click="changePage(page)">{{ page }}</button>
        </li>
        <li class="page-item" :class="{ disabled: currentPage === pages }">
          <button class="page-link" @click="changePage(currentPage + 1)" :disabled="currentPage === pages"><i
              class="bi bi-arrow-right"></i></button>
        </li>
      </ul>
    </nav>
</nav>
</template>
<style lang="scss" scope>
.sidebar{
    border: 1px solid;
    color: #black;
}
.city-card{
    img{
        width: 10rem;
}
}
    
</style>