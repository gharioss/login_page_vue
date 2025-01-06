<template>
    <v-carousel>
        <v-carousel-item
        v-for="(item,i) in items"
        :key="i"
        :src="item.src"
        cover
        ></v-carousel-item>
  </v-carousel>

  <div class="d-flex justify-center">
    <v-card width="300px" 
          v-for="(product, index) in products"
          :key="index"
          :value="index">
      <v-card-title class="text-h6 text-md-h5 text-lg-h4">{{ product?.id }}</v-card-title>
      <v-card-text>
        {{ product.name}}
      </v-card-text>
    </v-card>
  </div>

</template>

<script setup lang="ts">
import { ref } from 'vue';

const items = [
    {
    src: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg',
    },
    {
    src: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg',
    },
    {
    src: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg',
    },
    {
    src: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg',
    },
]

const products = ref(null);
fetch('https://testapi.jasonwatmore.com/products')
    .then(response => response.json())
    .then(data => products.value = data);
</script>