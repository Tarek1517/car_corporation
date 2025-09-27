<script setup>
import { ref } from 'vue';

const cars = ref([
  { image: '/images/honda-accord.png' },
  { image: '/images/nissan (2).png'},
  { image: '/images/accord-new-web.png' },
  { image: '/images/city-new-web.png'},
  { image: '/images/brv_slider_new.png' },
  { image: '/images/crossred.jpeg' },
  { image: '/images/Rav4.jpeg' },
  { image: '/images/rav4-1.jpg' },
  { image: '/images/rav4-2.png' },
  { image: '/images/rav4-3.jpg' },

]);
</script>

<template>
    <section class="w-full relative overflow-hidden py-2 md:py-6 bg-gradient-to-br from-slate-50 via-white to-slate-100">
    <div class="absolute top-0 right-0 w-96 h-96 bg-primary/10 rounded-full -translate-y-1/3 translate-x-1/3 blur-3xl animate-pulse-slow"></div>
    <div class="absolute bottom-0 left-0 w-[32rem] h-[32rem] bg-secondary/10 rounded-full translate-y-1/3 -translate-x-1/3 blur-3xl animate-pulse-slow delay-1000"></div>
    <div class="absolute top-1/2 left-1/4 w-64 h-64 bg-primary/5 rounded-full blur-3xl animate-pulse-slow delay-500"></div>
    <div class="absolute inset-0 opacity-[0.03] bg-grid-pattern"></div>
    <div class="container mx-auto px-4 py-8 md:py-16">
      <h1 class="text-3xl md:text-4xl font-extrabold text-gray-900 text-center mb-8 md:mb-12">
        Delivered Cars To Our Customer
      </h1>
      <p class="text-center text-gray-600 max-w-2xl mx-auto mb-10">
        Here are some of the cars we have successfully delivered to our happy customers. Each car is a testament to our commitment to quality and service.
      </p>

      <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
        <div
          v-for="(car, index) in cars"
          :key="index"
          class="relative bg-white rounded-xl shadow-lg overflow-hidden group hover:shadow-xl transition-shadow"
        >
  <NuxtLink to="/about/single-story">
    <img
      :src="car.image"
      alt="Delivered Car"
      class="w-full h-full object-cover transition-transform group-hover:scale-105"
    />
  </NuxtLink>
        </div>
      </div>
    </div>
    </section>
</template>
<style scoped>

</style>
