<script setup>
import { Icon } from '@iconify/vue';
import { ref } from 'vue';
import CarCard from '~/components/CarCard.vue';

const carsDetails = [
  {
    id: 1,
    type: "SUV",
    name: "Toyota RAV4",
    year: 2022,
    make: "Toyota",
    image: "/images/Rav4.jpeg",
    price: "$32,450",
    mileage: "18,240 mi",
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
];

const cars = ref([
  { src: "/images/crossred.jpeg" },
  { src: "/images/Rav4.jpeg" },
  { src: "/images/rav4-1.jpg" },
  { src: "/images/rav4-2.png" },
  { src: "/images/rav4-3.jpg" },
]);

const activeImage = ref(cars.value[0].src);
const currentIndex = ref(0);

const setActiveImage = (src, index) => {
  activeImage.value = src;
  currentIndex.value = index;
};

const nextImage = () => {
  currentIndex.value = (currentIndex.value + 1) % cars.value.length;
  activeImage.value = cars.value[currentIndex.value].src;
};

const prevImage = () => {
  currentIndex.value = (currentIndex.value - 1 + cars.value.length) % cars.value.length;
  activeImage.value = cars.value[currentIndex.value].src;
};
</script>

<template>
  <section class="min-h-screen bg-gray-50">
    <div class="container mx-auto px-4 py-8">
      <div class="mb-8">
        <h1 class="text-3xl font-bold text-gray-900 mb-2">Toyota - Corolla Cross - 2022 - Hybrid Z</h1>
      </div>
      <div class="flex flex-col lg:flex-row gap-8">
        <div class="lg:w-3/5">
          <div class="flex flex-col gap-4">
            <div class="flex-1 relative rounded-xl overflow-hidden shadow-lg">
              <img 
                :src="activeImage" 
                class="w-full h-80 lg:h-[500px] object-cover transition-opacity duration-300" 
                alt="Toyota Corolla Cross" 
              />
              <button
                class="absolute top-1/2 left-4 -translate-y-1/2 bg-white/90 p-3 rounded-full shadow-lg hover:bg-white transition-all duration-300 hover:scale-110"
                @click="prevImage"
              >
                <Icon icon="mdi:chevron-left" class="w-6 h-6 text-gray-700" />
              </button>
              <button
                class="absolute top-1/2 right-4 -translate-y-1/2 bg-white/90 p-3 rounded-full shadow-lg hover:bg-white transition-all duration-300 hover:scale-110"
                @click="nextImage"
              >
                <Icon icon="mdi:chevron-right" class="w-6 h-6 text-gray-700" />
              </button>
            </div>
            <div class="flex gap-3 overflow-x-auto py-2 px-1">
              <img 
                v-for="(car, index) in cars" 
                :key="index" 
                :src="car.src" 
                @click="setActiveImage(car.src, index)"
                class="w-24 h-20 object-cover rounded-lg cursor-pointer border-2 transition-all duration-300 hover:shadow-md"
                :class="currentIndex === index ? 'border-red-500 shadow-md' : 'border-gray-200 hover:border-gray-400'" 
              />
            </div>
          </div>
        </div>
        <div class="lg:w-2/5">
          <div class="mb-6 bg-white p-5 rounded-xl shadow-sm">
            <div class="flex items-center justify-between mb-4">
              <span class="text-gray-700 font-medium text-xl">Price:</span>
              <span class="text-red-600 font-bold text-3xl">$32,000</span>
            </div>
            <div class="text-sm text-gray-500">
              <p>Financing available with approved credit</p>
            </div>
          </div>
          <div class="bg-white rounded-xl shadow-sm p-5 mb-6">
            <h2 class="text-xl font-bold text-gray-800 mb-4">Vehicle Details</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
              <div class="space-y-4">
                <div>
                  <h3 class="text-sm font-medium text-gray-500">Manufacturer</h3>
                  <p class="text-gray-900 font-medium">Toyota</p>
                </div>
                <div>
                  <h3 class="text-sm font-medium text-gray-500">Model</h3>
                  <p class="text-gray-900 font-medium">Corolla Cross</p>
                </div>
                <div>
                  <h3 class="text-sm font-medium text-gray-500">Package</h3>
                  <p class="text-gray-900 font-medium">Hybrid Z</p>
                </div>
                <div>
                  <h3 class="text-sm font-medium text-gray-500">Year</h3>
                  <p class="text-gray-900 font-medium">2022</p>
                </div>
              </div>
              <div class="space-y-4">
                <div>
                  <h3 class="text-sm font-medium text-gray-500">Exterior Color</h3>
                  <p class="text-gray-900 font-medium">Pearl</p>
                </div>
                <div>
                  <h3 class="text-sm font-medium text-gray-500">Interior Color</h3>
                  <p class="text-gray-900 font-medium">Black</p>
                </div>
                <div>
                  <h3 class="text-sm font-medium text-gray-500">Chassis No</h3>
                  <p class="text-gray-900 font-medium">276511</p>
                </div>
                <div>
                  <h3 class="text-sm font-medium text-gray-500">Auditor Grade</h3>
                  <p class="text-gray-900 font-medium">4.0</p>
                </div>
              </div>
            </div>
          </div>
          <div class="space-y-4">
            <button class="w-full bg-green-500 text-white py-3 rounded-xl hover:bg-green-600 transition-all duration-300 flex items-center justify-center gap-2 font-medium shadow-md hover:shadow-lg">
              <Icon icon="mdi:whatsapp" class="w-5 h-5" />
              Chat Via WhatsApp
            </button>

            <div class="grid grid-cols-2 gap-3">
              <button class="bg-red-600 hover:bg-red-700 text-white font-medium py-3 px-4 rounded-xl transition-all duration-300 shadow-md hover:shadow-lg">
                Book a Test Drive
              </button>
              <button class="bg-white border border-red-600 text-red-600 hover:bg-red-50 font-medium py-3 px-4 rounded-xl transition-all duration-300 shadow-sm hover:shadow-md">
                Get a Quote
              </button>
            </div>
            
            <button class="w-full bg-gray-800 hover:bg-gray-900 text-white font-medium py-3 rounded-xl transition-all duration-300 shadow-md hover:shadow-lg">
              Add to Compare
            </button>
          </div>
        </div>
      </div>
    </div>

    <div class="h-px bg-gradient-to-r from-gray-300 via-gray-400 to-gray-300 my-12 max-w-7xl mx-auto"></div>

    <section class="max-w-7xl mx-auto px-4 pb-16">
      <h2 class="text-3xl font-bold text-gray-800 mb-6">Related Cars</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <CarCard 
          v-for="car in carsDetails" 
          :key="car.id" 
          :car="car"
          class="w-full transform hover:scale-105 transition-transform duration-300 shadow-md hover:shadow-xl" 
        />
      </div>
    </section>
  </section>
</template>

<style scoped>
.overflow-x-auto::-webkit-scrollbar {
  height: 6px;
}

.overflow-x-auto::-webkit-scrollbar-track {
  background: #f1f1f1;
  border-radius: 10px;
}

.overflow-x-auto::-webkit-scrollbar-thumb {
  background: #c1c1c1;
  border-radius: 10px;
}

.overflow-x-auto::-webkit-scrollbar-thumb:hover {
  background: #a8a8a8;
}
</style>