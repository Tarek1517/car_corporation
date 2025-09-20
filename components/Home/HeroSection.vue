<script setup lang="ts">
import { ref } from "vue";

const cars = [
  { name: "Toyota RAV4", image: "/images/Rav4.jpeg" },
  { name: "Toyota Corolla Cross", image: "/images/cross 1.jpeg" },
  { name: "Toyota Harrier", image: "/images/Harrier.jpeg" },
  { name: "Corolla Cross", image: "/images/crossred.jpeg" },
  { name: "Toyota Cross", image: "/images/toyotacorollacross.jpeg" },
  { name: "Toyota NOAH", image: "/images/noah.jpeg" },
  { name: "Honda Civic", image: "/images/civik2.png" },
];

const activeIndex = ref<number | null>(null);

const getCarName = (carName: string, index: number) => {
  if (activeIndex.value === null) return carName;
  if (index === activeIndex.value) return carName;

  const words = carName.split(" ");
  return words.slice(0, 2).join(" ");
};
</script>

<template>
  <section class="w-full relative overflow-hidden">
    <div class="flex w-full h-auto">
      <div
        v-for="(car, index) in cars"
        :key="index"
        class="group relative h-full flex flex-col overflow-hidden transition-all duration-500 flex-1 hover:flex-[6] hover:z-10 min-w-0"
        @mouseenter="activeIndex = index"
        @mouseleave="activeIndex = null"
      >
        <!-- Car Image -->
         <NuxtLink to="/cars/car-details">
                  <div class="h-[550px] w-full overflow-hidden relative">
          <img
            :src="car.image"
            :alt="car.name"
            class="h-full w-auto object-cover object-[10%_center] transition-all duration-500 ease-[cubic-bezier(0.25,0.1,0.25,1)] group-hover:object-[10%_center] group-hover:scale-[1.15] brightness-95 group-hover:brightness-100"
          />
        </div>
         </NuxtLink>

        <!-- Red Bar with Car Name -->
        <div
          class="bg-gradient-to-r from-red-600 to-red-500 text-white text-center py-3 text-sm md:text-base font-semibold tracking-wide transition-all duration-500 group-hover:py-5"
        >
          {{ getCarName(car.name, index) }}
        </div>
      </div>
    </div>
  </section>
</template>
