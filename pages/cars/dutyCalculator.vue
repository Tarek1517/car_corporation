<script setup>
import { ref } from 'vue';
import { Icon } from '@iconify/vue';
const carValue = ref(10000);
const engineCapacity = ref(1800); 
const carAge = ref(3); 
const calculatedDuty = ref(null); 
const hasCalculated = ref(false); 

const calculateDuty = () => {
  let duty = 0;
  const value = parseFloat(carValue.value);
  const capacity = parseFloat(engineCapacity.value);
  const age = parseFloat(carAge.value);

  console.log("Inputs:", { value, capacity, age }); 

  if (isNaN(value) || value <= 0) {
    calculatedDuty.value = "0.00";
    hasCalculated.value = true;
    return;
  }

  duty += value * 0.25; 

  if (capacity > 2000) {
    duty += value * 0.15; 
  } else if (capacity > 1500) {
    duty += value * 0.10;
  }

  if (age > 0) {
    const depreciationRate = Math.min(age, 5) * 0.05;
    duty -= value * depreciationRate;
  }

  calculatedDuty.value = Math.max(0, duty).toFixed(2); 
  hasCalculated.value = true;
  console.log("Calculated duty:", calculatedDuty.value);
};
</script>
<template>

  <div class="w-full">
    <div class="flex items-start mb-6">
      <h2 class="text-3xl font-bold text-gray-800">Duty Calculator</h2>
      <div class="ml-4 bg-primary/10 text-primary px-3 py-1 rounded-full text-sm flex items-center">
        <Icon icon="mdi:calculator" class="w-4 h-4 mr-1" /> Estimate Import Costs
      </div>
    </div>
    
    <div class="bg-white rounded-xl shadow-md p-6 border border-gray-100">
      <p class="text-gray-600 mb-6">Calculate estimated import duties based on vehicle value, engine size, and age.</p>
      
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
        <div class="relative">
          <label for="carValue" class="block text-sm font-medium text-gray-700 mb-2">
            <Icon icon="mdi:currency-usd" class="w-4 h-4 inline mr-1 text-primary" /> Vehicle Price ($)
          </label>
          <div class="relative">
            <span class="absolute inset-y-0 left-0 pl-3 flex items-center text-gray-500">$</span>
            <input 
              type="number" 
              name="carValue" 
              id="carValue" 
              v-model="carValue"
              min="0"
              step="100"
              class="pl-8 block w-full px-4 py-3 bg-gray-50 border border-gray-300 rounded-lg shadow-sm focus:outline-none focus:ring-2 focus:ring-primary focus:border-primary sm:text-sm transition"
            >
          </div>
        </div>
        
        <div class="relative">
          <label for="engineCapacity" class="block text-sm font-medium text-gray-700 mb-2">
            <Icon icon="mdi:engine" class="w-4 h-4 inline mr-1 text-primary" /> Engine Capacity (CC)
          </label>
          <input 
            type="number" 
            name="engineCapacity" 
            id="engineCapacity" 
            v-model="engineCapacity"
            min="0"
            step="100"
            class="block w-full px-4 py-3 bg-gray-50 border border-gray-300 rounded-lg shadow-sm focus:outline-none focus:ring-2 focus:ring-primary focus:border-primary sm:text-sm transition"
          >
        </div>
        
        <div class="relative">
          <label for="carAge" class="block text-sm font-medium text-gray-700 mb-2">
            <Icon icon="mdi:calendar-clock" class="w-4 h-4 inline mr-1 text-primary" /> Vehicle Age (years)
          </label>
          <input 
            type="number" 
            name="carAge" 
            id="carAge" 
            v-model="carAge"
            min="0"
            max="20"
            class="block w-full px-4 py-3 bg-gray-50 border border-gray-300 rounded-lg shadow-sm focus:outline-none focus:ring-2 focus:ring-primary focus:border-primary sm:text-sm transition"
          >
        </div>
      </div>
      
      <div class="mt-8">
        <button 
          @click="calculateDuty"
          type="button"
          class="w-full flex justify-center items-center px-6 py-4 bg-gradient-to-r from-primary to-secondary hover:from-primary hover:to-secondary text-white font-medium rounded-lg shadow-md hover:shadow-lg transition-all duration-300 transform hover:-translate-y-0.5 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-primary"
        >
          <Icon icon="mdi:calculator-variant" class="mr-2 h-5 w-5" />
          Calculate Import Duty
          <Icon icon="mdi:arrow-right" class="ml-2 h-5 w-5" />
        </button>
      </div>
      
      <div v-if="hasCalculated" class="mt-8 p-6 bg-gradient-to-r from-primary/5 to-primary/10 rounded-xl border border-primary/20">
        <div class="flex items-center justify-between">
          <div>
            <h3 class="text-lg font-semibold text-gray-800">Estimated Import Duty</h3>
            <p class="text-gray-600 text-sm mt-1">Based on current regulations and rates</p>
          </div>
          <div class="text-right">
            <div class="text-3xl font-bold text-primary">${{ calculatedDuty }}</div>
            <div class="text-gray-600 text-sm mt-1">Estimated total cost</div>
          </div>
        </div>
        
        <div class="mt-4 pt-4 border-t border-primary/20">
          <div class="flex items-center text-sm text-gray-600">
            <Icon icon="mdi:information-outline" class="w-4 h-4 mr-2 text-primary" />
            This is an estimate only. Actual duties may vary based on current regulations, taxes, and additional fees.
          </div>
        </div>
      </div>
      
      <div v-else class="mt-8 p-4 bg-gray-50 rounded-lg border border-gray-200 text-center">
        <Icon icon="mdi:lightbulb-on-outline" class="w-8 h-8 text-gray-400 mx-auto mb-2" />
        <p class="text-gray-500">Enter vehicle details and click "Calculate" to estimate import duties</p>
      </div>
    </div>
  </div>
</template>