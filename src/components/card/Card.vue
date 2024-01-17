<script setup lang="ts">
import { useCityStore } from '@/stores/cityStore';
interface City {
    id: number;
    image: string;
    description: string;
    title: string;
}
</script>
<template>
    <div v-for="(city, index) in " :key="city.id" class="citi-card card" style="width: 18rem;">
        <img :src="city.image" :alt="city.title" class="card-img-top">
        <div class="card-body">
            <h3 class="card-title">{{ city.title }}</h3>
            <p class="card-text">{{ city.description }}</p> 
        </div>
        <div>
            <a href="#" class="btn btn-primary">More</a>   
        </div>
    </div>
</template>