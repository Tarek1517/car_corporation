<script setup lang="ts">
const cars = [
  { name: "City", image: "/images/city-new-web.png" },
  { name: "Civic Turbo", image: "/images/civic_new_banner_2021.png" },
  { name: "Accord Turbo", image: "/images/accord-new-web.png" },
  { name: "HR-V", image: "/images/hrv-2.png" },
  { name: "New BR-V", image: "/images/brv_slider_new.png" },
  { name: "Honda CR-V", image: "/images/crv-new-web.png" },
  { name: "CR-V Turbo", image: "/images/crv-2024.png" },
];
</script>

<template>
  <section class="w-full relative overflow-hidden">
    <!-- Cars Row -->
    <div class="flex w-full h-auto">
      <div
        v-for="(car, index) in cars"
        :key="index"
        class="group relative h-full flex flex-col overflow-hidden transition-all duration-500 flex-1 hover:flex-[6] hover:z-10 min-w-0"
      >
        <!-- Car Image Container with focus on front of car -->
        <div class="h-[500px] w-full overflow-hidden relative">
          <img
            :src="car.image"
            :alt="car.name"
            class="h-full w-auto object-cover object-[10%_center] transition-all duration-500 ease-[cubic-bezier(0.25,0.1,0.25,1)] group-hover:object-[10%_center] group-hover:scale-[1.15] brightness-95 group-hover:brightness-100"
          />
          
        </div>

        <!-- Red Bar with Car Name -->
        <div
          class="bg-gradient-to-r from-red-600 to-red-500 text-white text-center py-3 text-sm md:text-base font-semibold tracking-wide transition-all duration-500 group-hover:py-5"
        >
          {{ car.name }}
        </div>
      </div>
    </div>
  </section>
</template>