<script setup>
import { ref } from "vue";

// Cars data
const cars = [
  {
    id: 1,
    type: "SUV",
    name: "Toyota RAV4",
    year: 2022,
    make: "Toyota",
    image: "/images/Rav4.jpeg",
    price: "$32,450",
    mileage: "18,240 mi",
    condition: "Used"
  },
  {
    id: 2,
    type: "SUV",
    name: "Toyota Corolla Cross",
    year: 2022,
    make: "Toyota",
    image: "/images/cross 1.jpeg",
    price: "$28,900",
    mileage: "12,150 mi",
    condition: "New"
  },
  {
    id: 3,
    type: "SUV",
    name: "Toyota Harrier",
    year: 2021,
    make: "Toyota",
    image: "/images/Harrier.jpeg",
    price: "$36,750",
    mileage: "22,405 mi",
   
  },
  {
    id: 4,
    type: "SUV",
    name: "Corolla Cross",
    year: 2020,
    make: "Toyota",
    image: "/images/crossred.jpeg",
    price: "$26,800",
    mileage: "30,120 mi",
    condition: "New"
  },
  {
    id: 5,
    type: "SUV",
    name: "Toyota Cross",
    year: 2021,
    make: "Toyota",
    image: "/images/toyotacorollacross.jpeg",
    price: "$29,500",
    mileage: "15,670 mi",
    condition: "New"
  },
  {
    id: 6,
    type: "Van",
    name: "Toyota NOAH",
    year: 2020,
    make: "Toyota",
    image: "/images/noah.jpeg",
    price: "$31,200",
    mileage: "25,890 mi",
    condition: "Used"
  },
  {
    id: 7,
    type: "Sedan",
    name: "Honda Civic",
    year: 2019,
    make: "Honda",
    image: "/images/civik2.png",
    price: "$23,900",
    mileage: "35,405 mi",
    condition: "New"
  },
];

const visibleCars = ref(6);
const showMore = () => {
  visibleCars.value += 3;
  if (visibleCars.value >= cars.length) {
    visibleCars.value = cars.length;
  }
};
</script>

<template>
  <section class="py-16 bg-gradient-to-b from-primary/10 to-white relative overflow-hidden">
    <!-- Decorative elements -->
    <div class="absolute top-0 left-0 w-72 h-72 bg-primary/5 rounded-full -translate-x-1/2 -translate-y-1/2 blur-3xl"></div>
    <div class="absolute bottom-0 right-0 w-96 h-96 bg-secondary/5 rounded-full translate-x-1/3 translate-y-1/3 blur-3xl"></div>
    
    <div class="container mx-auto px-6 relative z-10">
      <!-- Section Header -->
      <div class="text-center mb-16">
        <div class="inline-flex items-center px-4 py-2 bg-primary/10 text-primary rounded-full text-sm font-semibold mb-4">
          <Icon name="heroicons:sparkles" class="w-4 h-4 mr-2" />
          Premium Collection
        </div>
        <h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-4">
          Discover Your Perfect <span class="text-primary">Vehicle</span>
        </h2>
        <p class="text-xl text-gray-600 max-w-5xl mx-auto">
          Explore our curated selection of premium vehicles, each meticulously inspected for quality and performance.
        </p>
      </div>
      <!-- Cars Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 mb-16">
        <CarCard
          v-for="car in cars.slice(0, visibleCars)"
          :key="car.id"
          :car="car"
          class="w-full transform hover:scale-105 transition-transform duration-300"
        />
      </div>
    </div>
  </section>
</template>

<style scoped>

</style>