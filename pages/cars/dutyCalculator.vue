<script setup>
import { ref, computed } from 'vue';
import { Icon } from '@iconify/vue';

const carData = {
  'Toyota': {
    'Corolla': {
      'engine_capacities': [1500, 1800],
      'chassis_codes': ['ZRE152', 'ZRE152N']
    },
    'Camry': {
      'engine_capacities': [2000, 2500],
      'chassis_codes': ['ACV40', 'ACV40N']
    }
  },
  'Honda': {
    'Civic': {
      'engine_capacities': [1600, 1800],
      'chassis_codes': ['FD1', 'FD2']
    }
  }
};

const selectedBrand = ref('');
const selectedModel = ref('');
const selectedChassis = ref('');
const selectedYear = ref('');
const selectedCc = ref('');
const calculatedDuty = ref(null);
const hasCalculated = ref(false);

const years = ref(Array.from({length: 10}, (_, i) => new Date().getFullYear() - i));

const availableModels = computed(() => {
  return selectedBrand.value ? Object.keys(carData[selectedBrand.value]) : [];
});

const availableChassis = computed(() => {
  return selectedBrand.value && selectedModel.value ? carData[selectedBrand.value][selectedModel.value].chassis_codes : [];
});

const availableCcs = computed(() => {
  return selectedBrand.value && selectedModel.value ? carData[selectedBrand.value][selectedModel.value].engine_capacities : [];
});

const calculateDuty = () => {
  let duty = 0;
  const value = 10000;
  const capacity = parseFloat(selectedCc.value);
  const age = new Date().getFullYear() - parseFloat(selectedYear.value);

  if (isNaN(value) || value <= 0 || !selectedCc.value) {
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
};
</script>

<template>
<section class="w-full bg-white text-gray-800 overflow-hidden flex justify-center py-12">
  <div class="max-w-4xl w-full mx-auto px-4 relative z-10">
    <div class="flex flex-col items-center mb-8 text-center">
      <h2 class="text-3xl font-bold text-gray-800 mb-4">Duty Calculator</h2>
      <div class="bg-red-600/10 text-red-600 px-3 py-1 rounded-full text-sm flex items-center">
        <Icon icon="mdi:calculator" class="w-4 h-4 mr-1" /> Estimate Import Costs
      </div>
    </div>

    <div class="bg-white shadow-lg p-8 border border-gray-100 rounded-xl">
      <p class="text-gray-600 mb-8 text-center">Calculate estimated import duties based on vehicle details.</p>

      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        <div class="relative z-10">
          <label for="brand" class="block text-sm font-medium text-gray-700 mb-2">
            <Icon icon="mdi:car-multiple" class="w-4 h-4 inline mr-1 text-red-600" /> Select A Brand
          </label>
          <select v-model="selectedBrand" id="brand" class="block w-full px-4 py-3 bg-gray-50 border border-gray-300 rounded-lg shadow-sm focus:outline-none focus:ring-2 focus:ring-red-600 focus:border-red-600 sm:text-sm transition">
            <option disabled value="">Please Select A Brand</option>
            <option v-for="brand in Object.keys(carData)" :key="brand" :value="brand">{{ brand }}</option>
          </select>
        </div>

        <div class="relative">
          <label for="model" class="block text-sm font-medium text-gray-700 mb-2">
            <Icon icon="mdi:car-info" class="w-4 h-4 inline mr-1 text-red-600" /> Select A Model
          </label>
          <select v-model="selectedModel" id="model" :disabled="!selectedBrand" class="block w-full px-4 py-3 bg-gray-50 border border-gray-300 rounded-lg shadow-sm focus:outline-none focus:ring-2 focus:ring-red-600 focus:border-red-600 sm:text-sm transition disabled:opacity-50">
            <option disabled value="">Please Select A Model</option>
            <option v-for="model in availableModels" :key="model" :value="model">{{ model }}</option>
          </select>
        </div>

        <div class="relative">
          <label for="chassis" class="block text-sm font-medium text-gray-700 mb-2">
            <Icon icon="mdi:code-tags" class="w-4 h-4 inline mr-1 text-red-600" /> Select A Chassis Code
          </label>
          <select v-model="selectedChassis" id="chassis" :disabled="!selectedModel" class="block w-full px-4 py-3 bg-gray-50 border border-gray-300 rounded-lg shadow-sm focus:outline-none focus:ring-2 focus:ring-red-600 focus:border-red-600 sm:text-sm transition disabled:opacity-50">
            <option disabled value="">Please Select A Chassis Code</option>
            <option v-for="chassis in availableChassis" :key="chassis" :value="chassis">{{ chassis }}</option>
          </select>
        </div>

        <div class="relative">
          <label for="year" class="block text-sm font-medium text-gray-700 mb-2">
            <Icon icon="mdi:calendar" class="w-4 h-4 inline mr-1 text-red-600" /> Choose Year
          </label>
          <select v-model="selectedYear" id="year" class="block w-full px-4 py-3 bg-gray-50 border border-gray-300 rounded-lg shadow-sm focus:outline-none focus:ring-2 focus:ring-red-600 focus:border-red-600 sm:text-sm transition">
            <option disabled value="">Choose Year</option>
            <option v-for="year in years" :key="year" :value="year">{{ year }}</option>
          </select>
        </div>

        <div class="relative">
          <label for="cc" class="block text-sm font-medium text-gray-700 mb-2">
            <Icon icon="mdi:engine" class="w-4 h-4 inline mr-1 text-red-600" /> Choose CC
          </label>
          <select v-model="selectedCc" id="cc" :disabled="!selectedModel" class="block w-full px-4 py-3 bg-gray-50 border border-gray-300 rounded-lg shadow-sm focus:outline-none focus:ring-2 focus:ring-red-600 focus:border-red-600 sm:text-sm transition disabled:opacity-50">
            <option disabled value="">Choose CC</option>
            <option v-for="cc in availableCcs" :key="cc" :value="cc">{{ cc }}</option>
          </select>
        </div>
      </div>

      <div class="mt-10">
        <button
          @click="calculateDuty"
          type="button"
          class="w-full flex justify-center items-center px-6 py-4 bg-red-600 text-white font-medium rounded-lg shadow-md hover:bg-red-700 transition-all duration-300 transform hover:-translate-y-0.5 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-red-600"
        >
          <Icon icon="mdi:calculator-variant" class="mr-2 h-5 w-5" />
          Calculate Import Duty
          <Icon icon="mdi:arrow-right" class="ml-2 h-5 w-5" />
        </button>
      </div>

      <div v-if="hasCalculated" class="mt-8 p-6 bg-red-600/5 rounded-xl border border-red-600/20">
        <div class="flex items-center justify-between">
          <div>
            <h3 class="text-lg font-semibold text-gray-800">Estimated Import Duty</h3>
            <p class="text-gray-600 text-sm mt-1">Based on selected details</p>
          </div>
          <div class="text-right">
            <div class="text-3xl font-bold text-red-600">${{ calculatedDuty }}</div>
            <div class="text-gray-600 text-sm mt-1">Estimated total cost</div>
          </div>
        </div>

        <div class="mt-4 pt-4 border-t border-red-600/20">
          <div class="flex items-center text-sm text-gray-600">
            <Icon icon="mdi:information-outline" class="w-4 h-4 mr-2 text-red-600" />
            This is an estimate only. Actual duties may vary based on current regulations, taxes, and additional fees.
          </div>
        </div>
      </div>

      <div v-else class="mt-8 p-6 bg-gray-50 rounded-lg border border-gray-200 text-center">
        <Icon icon="mdi:lightbulb-on-outline" class="w-8 h-8 text-gray-400 mx-auto mb-2" />
        <p class="text-gray-500">Enter vehicle details and click "Calculate" to estimate import duties</p>
      </div>
    </div>
  </div>
</section>
</template>
<style scoped>
</style>