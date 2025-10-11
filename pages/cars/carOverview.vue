<script setup>
import { Icon } from "@iconify/vue";
const carOverview = [
  { icon: "mdi:car-suv", label: "Body", value: "SUV" },
  { icon: "mdi:counter", label: "Mileage", value: "50" },
  { icon: "mdi:gas-station", label: "Fuel Type", value: "Petrol" },
  { icon: "mdi:calendar", label: "Year", value: "2023" },
  { icon: "mdi:car-shift-pattern", label: "Transmission", value: "Automatic" },
  { icon: "mdi:car", label: "Drive Type", value: "All-Wheel Drive (AWD/4WD)" },
  { icon: "mdi:account-check", label: "Condition", value: "New" },
  { icon: "mdi:engine", label: "Engine Size", value: "4.5" },
  { icon: "mdi:car-door", label: "Door", value: "4 Doors" },
  { icon: "mdi:cylinder", label: "Cylinder", value: "10" },
  { icon: "mdi:palette", label: "Color", value: "Black, Gold, White" },
  { icon: "mdi:card-account-details-outline", label: "VIN", value: "MCB123813" },
];
</script>
<template>
  <section class="max-w-7xl mx-auto px-4 py-8">
     <div class="w-full h-[1px] bg-gradient-to-r from-gray-300 via-gray-400 to-gray-300 my-8"></div>
    <div class="mb-8 text-start">
      <h2 class="text-3xl font-bold text-gray-800 mb-2">Car Overview</h2>
    </div>
    
    <div class="flex flex-col lg:flex-row gap-8">
        <div class="grid grid-cols-1 sm:grid-cols-4 lg:grid-cols-6 gap-4">
          <div
            v-for="(item, index) in carOverview"
            :key="index"
            class="bg-white rounded-xl p-2 shadow-sm hover:shadow-md transition-all duration-300 border border-gray-100 hover:border-primary"
          >
            <div class="flex items-start space-x-3">
              <div class="bg-blue-50 p-2 rounded-lg">
                <Icon :icon="item.icon" class="text-primary w-6 h-6" />
              </div>
              <div>
                <p class="text-sm text-gray-500">{{ item.label }}</p>
                <p class="font-semibold text-xs text-gray-800">{{ item.value }}</p>
              </div>
            </div>
          </div>
        </div>
      
      <div class="lg:w-1/3">
        <div class="bg-white rounded-xl shadow-lg p-6 sticky top-6">
          <div class="text-center mb-6">
            <img src="/images/avater1.png" alt="Admin Avatar" class="w-24 h-24 rounded-full object-cover mx-auto mb-4 border-4 border-blue-50" />
            <h3 class="text-xl font-bold text-gray-800">Car Corporation</h3>
            <p class="text-gray-600 flex items-center justify-center mt-1">
              <Icon icon="mdi:map-marker" class="mr-1 text-gray-500" />
              Dhaka 1212
            </p>
          </div>
          
          <div class="flex justify-center gap-4 mb-6">
            <a href="tel:+88123456789" class="flex flex-col items-center text-white transition">
              <div class="w-12 h-12 rounded-full bg-primary flex items-center justify-center mb-1">
                <Icon icon="mdi:phone" class="w-6 h-6" />
              </div>
              <span class="text-sm text-gray-600">Call Now</span>
            </a>
          </div>
          
          <div class="space-y-3">            
            <button class="w-full bg-green-500 text-white py-3 rounded-lg hover:bg-green-600 transition flex items-center justify-center gap-2 font-medium">
              <Icon icon="mdi:whatsapp" class="w-5 h-5" />
              Chat Via WhatsApp
            </button>
          </div>
          
          <a href="#" class="block text-center text-blue-600 mt-6 hover:underline font-medium">
            View All Stock at This Dealer
            <Icon icon="mdi:arrow-right" class="w-4 h-4 inline-block ml-1" />
          </a>
        </div>
      </div> 
    </div>
  </section>
</template>