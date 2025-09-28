<script setup>
import { ref, computed, onMounted } from "vue";
import { Icon } from '@iconify/vue';
import CarCard from "~/components/CarCard.vue";

const isSidebarOpen = ref(false);
const typeFilter = ref([]);
const conditionFilter = ref([]);
const yearFilter = ref([]);
const transmissionFilter = ref([]);
const fuelTypeFilter = ref([]);
const searchQuery = ref('');
const visibleCars = ref(6);
const selectedCar = ref(null);
const showCarDetails = ref(false);
const sortBy = ref('default');
const viewMode = ref('grid'); 
const priceRange = ref([0, 50000]);
const minPrice = computed(() => Math.min(...cars.map(car => car.price)));
const maxPrice = computed(() => Math.max(...cars.map(car => car.price)));
onMounted(() => {
  priceRange.value = [minPrice.value, maxPrice.value];
});

const carTypes = computed(() => [...new Set(cars.map(car => car.type))]);
const carConditions = computed(() => [...new Set(cars.map(car => car.condition))]);
const carYears = computed(() => [...new Set(cars.map(car => car.year))].sort((a, b) => b - a));
const carTransmissions = computed(() => [...new Set(cars.map(car => car.transmission))]);
const carFuelTypes = computed(() => [...new Set(cars.map(car => car.fuelType))]);

const filteredCars = computed(() => {
  let result = [...cars];
  if (searchQuery.value) {
    const query = searchQuery.value.toLowerCase();
    result = result.filter(car => 
      car.name.toLowerCase().includes(query) || 
      car.make.toLowerCase().includes(query) ||
      car.type.toLowerCase().includes(query)
    );
  }

  if (typeFilter.value.length > 0) {
    result = result.filter(car => typeFilter.value.includes(car.type));
  }

  if (conditionFilter.value.length > 0) {
    result = result.filter(car => conditionFilter.value.includes(car.condition));
  }

  if (yearFilter.value.length > 0) {
    result = result.filter(car => yearFilter.value.includes(car.year));
  }

  if (transmissionFilter.value.length > 0) {
    result = result.filter(car => transmissionFilter.value.includes(car.transmission));
  }

  if (fuelTypeFilter.value.length > 0) {
    result = result.filter(car => fuelTypeFilter.value.includes(car.fuelType));
  }

  result = result.filter(car => car.price >= priceRange.value[0] && car.price <= priceRange.value[1]);
  

  if (sortBy.value === 'price-low-high') {
    result.sort((a, b) => a.price - b.price);
  } else if (sortBy.value === 'price-high-low') {
    result.sort((a, b) => b.price - a.price);
  } else if (sortBy.value === 'year-new-old') {
    result.sort((a, b) => b.year - a.year);
  } else if (sortBy.value === 'year-old-new') {
    result.sort((a, b) => a.year - b.year);
  }
  
  return result;
});

const cars = [
  {
    id: 1,
    type: "SUV",
    name: "Toyota RAV4",
    year: 2022,
    make: "Toyota",
    image: "/images/Rav4.jpeg",
    price: 32450,
    mileage: "18,240 mi",
    condition: "Used",
    rating: 4.5,
    reviewCount: 128
  },
  {
    id: 2,
    type: "SUV",
    name: "Toyota Corolla Cross",
    year: 2022,
    make: "Toyota",
    image: "/images/cross 1.jpeg",
    price: 28900,
    mileage: "12,150 mi",
    condition: "New",
    rating: 4.2,
    reviewCount: 89
  },
  {
    id: 3,
    type: "SUV",
    name: "Toyota Harrier",
    year: 2021,
    make: "Toyota",
    image: "/images/Harrier.jpeg",
    price: 36750,
    mileage: "22,405 mi",
    rating: 4.8,
    reviewCount: 156
  },
  {
    id: 4,
    type: "SUV",
    name: "Corolla Cross",
    year: 2020,
    make: "Toyota",
    image: "/images/crossred.jpeg",
    price: 26800,
    mileage: "30,120 mi",
    condition: "New",
    rating: 3.9,
    reviewCount: 67
  },
  {
    id: 5,
    type: "SUV",
    name: "Toyota Cross",
    year: 2021,
    make: "Toyota",
    image: "/images/toyotacorollacross.jpeg",
    price: 29500,
    mileage: "15,670 mi",
    condition: "New",
    rating: 4.1,
    reviewCount: 94
  },
  {
    id: 6,
    type: "Van",
    name: "Toyota NOAH",
    year: 2020,
    make: "Toyota",
    image: "/images/noah.jpeg",
    price: 31200,
    mileage: "25,890 mi",
    condition: "Used",
    rating: 4.3,
    reviewCount: 112
  },
  {
    id: 7,
    type: "Sedan",
    name: "Honda Civic",
    year: 2019,
    make: "Honda",
    image: "/images/civik2.png",
    price: 23900,
    mileage: "35,405 mi",
    condition: "New",
    rating: 4.6,
    reviewCount: 203
  },
];



const resetFilters = () => {
  typeFilter.value = [];
  conditionFilter.value = [];
  yearFilter.value = [];
  transmissionFilter.value = [];
  fuelTypeFilter.value = [];
  searchQuery.value = '';
  priceRange.value = [minPrice.value, maxPrice.value];
  visibleCars.value = 6;
  sortBy.value = 'default';
};

const viewCarDetails = (car) => {
  selectedCar.value = car;
  showCarDetails.value = true;
  document.body.style.overflow = 'hidden';
};


const formatPrice = (price) => {
  return new Intl.NumberFormat('en-US', {
    style: 'currency',
    currency: 'USD',
    maximumFractionDigits: 0
  }).format(price);
};

</script>

<template>
  <section class="w-full relative overflow-hidden py-12 md:py-20 bg-gradient-to-br from-slate-900 via-slate-800 to-slate-900">
    <div class="absolute top-0 right-0 w-96 h-96 bg-primary/10 rounded-full -translate-y-1/3 translate-x-1/3 blur-3xl animate-pulse-slow"></div>
    <div class="absolute bottom-0 left-0 w-[32rem] h-[32rem] bg-secondary/10 rounded-full translate-y-1/3 -translate-x-1/3 blur-3xl animate-pulse-slow delay-1000"></div>
    <div class="absolute top-1/2 left-1/4 w-64 h-64 bg-primary/5 rounded-full blur-3xl animate-pulse-slow delay-500"></div>
    <div class="absolute inset-0 opacity-[0.03] bg-grid-pattern"></div>
    
    <div class="max-w-7xl mx-auto px-6 py-12 grid grid-cols-1 lg:grid-cols-2 items-center gap-10">
      <div class="text-left text-white space-y-6">
        <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold uppercase leading-tight">
          Find Your <span class="text-primary">Perfect</span> Car
        </h1>
        <p class="text-gray-300 text-lg md:text-xl max-w-md">
          Discover quality vehicles at competitive prices. Our curated selection ensures you find the car that fits your lifestyle.
        </p>
        <div class="flex flex-wrap gap-4 pt-4">
          <div class="flex items-center gap-2 bg-white/10 backdrop-blur-sm px-4 py-2 rounded-full">
            <Icon icon="mdi:car" class="text-primary h-5 w-5" />
            <span class="text-sm font-medium">500+ Vehicles</span>
          </div>
          <div class="flex items-center gap-2 bg-white/10 backdrop-blur-sm px-4 py-2 rounded-full">
            <Icon icon="mdi:shield-check" class="text-primary h-5 w-5" />
            <span class="text-sm font-medium">Quality Assured</span>
          </div>
          <div class="flex items-center gap-2 bg-white/10 backdrop-blur-sm px-4 py-2 rounded-full">
            <Icon icon="mdi:finance" class="text-primary h-5 w-5" />
            <span class="text-sm font-medium">Financing Available</span>
          </div>
        </div>
      </div>
      <div class="flex justify-center lg:justify-end relative">
        <div class="relative">
          <div class="absolute -top-4 -right-4 w-24 h-24 bg-primary/20 rounded-full blur-xl"></div>
          <div class="absolute -bottom-4 -left-4 w-32 h-32 bg-secondary/20 rounded-full blur-xl"></div>
          <img src="../../public/images/honda-suv.png" alt="Japanese Car"
            class="w-full max-w-md drop-shadow-2xl relative z-10" />
        </div>
      </div>
    </div>
  </section>

  <section class="w-full py-8 bg-white border-b border-gray-200">
    <div class="max-w-7xl mx-auto px-6">
      <div class="max-w-2xl mx-auto">
        <div class="relative">
          <div class="absolute inset-y-0 left-0 flex items-center pl-4 pointer-events-none">
            <Icon icon="mdi:magnify" class="h-5 w-5 text-gray-400" />
          </div>
          <input 
            type="text" 
            v-model="searchQuery"
            placeholder="Search by make, model, or type..."
            class="w-full pl-12 pr-4 py-4 bg-gray-50 text-gray-500 border border-gray-300 rounded-xl focus:ring-2 focus:ring-primary focus:border-primary focus:bg-white transition-all"
          />
          <div class="absolute inset-y-0 right-0 flex items-center pr-4">
            <button @click="resetFilters" class="text-sm text-gray-500 hover:text-primary transition-colors">
              Clear
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section class="w-full relative overflow-hidden py-2 md:py-6 bg-gradient-to-br from-slate-50 via-white to-slate-100">
    <div class="bg-white border-b border-gray-200 shadow-sm px-4 py-1 sticky top-0 z-10">
      <div class="max-w-7xl mx-auto flex flex-col md:flex-row justify-between items-center pt-5">
        <div class="text-gray-700 text-sm pt-6">
          <p>{{ filteredCars.length }} vehicles found</p>
        </div>

        <div class="flex items-center gap-4 mt-4 md:mt-0">
          <div class="flex items-center gap-2">
            <span class="text-sm text-gray-600">Sort by:</span>
            <select v-model="sortBy" class="text-sm border border-gray-300 rounded-lg px-3 py-1.5 focus:ring-2 focus:ring-primary focus:border-primary">
              <option value="default">Default</option>
              <option value="price-low-high">Price: Low to High</option>
              <option value="price-high-low">Price: High to Low</option>
              <option value="year-new-old">Year: Newest First</option>
              <option value="year-old-new">Year: Oldest First</option>
            </select>
          </div>
          
          <div class="flex gap-2">
            <button 
              @click="viewMode = 'grid'" 
              :class="viewMode === 'grid' ? 'bg-gray-100 text-primary' : 'text-gray-600'"
              class="p-2 rounded-lg border border-gray-300 hover:bg-gray-50"
            >
              <Icon icon="mdi:view-grid" class="h-5 w-5" />
            </button>
            <button 
              @click="viewMode = 'list'" 
              :class="viewMode === 'list' ? 'bg-gray-100 text-primary' : 'text-gray-600'"
              class="p-2 rounded-lg border border-gray-300 hover:bg-gray-50"
            >
              <Icon icon="mdi:view-list" class="h-5 w-5" />
            </button>
          </div>
          
          <button 
            @click="isSidebarOpen = true"
            class="md:hidden flex items-center gap-2 px-4 py-2 bg-primary text-white rounded-lg"
          >
            <Icon icon="mdi:filter" class="h-5 w-5" />
            <span>Filters</span>
          </button>
        </div>
      </div>
    </div>

    <div class="max-w-7xl mx-auto py-4 pt-8">
      <div class="flex flex-col md:flex-row gap-6">
        <aside class="hidden md:block w-64 space-y-6">
          <div class="bg-white p-4 rounded-lg shadow-sm border border-gray-200">
            <div class="flex justify-between items-center mb-4">
              <h2 class="text-lg font-bold text-gray-800">Filters</h2>
              <button @click="resetFilters" class="text-primary text-sm font-medium hover:underline">
                Reset
              </button>
            </div>

            <div class="mb-6">
              <h3 class="font-semibold text-gray-700 mb-3">Price Range</h3>
              <div class="px-2">
                <input 
                  type="range" 
                  v-model="priceRange[0]" 
                  :min="minPrice" 
                  :max="maxPrice"
                  class="w-full text-primary mb-2" 
                />
                <input 
                  type="range" 
                  v-model="priceRange[1]" 
                  :min="minPrice" 
                  :max="maxPrice"
                  class="w-full accent-primary" 
                />
                <div class="flex justify-between mt-2 text-sm text-gray-600">
                  <span>{{ formatPrice(priceRange[0]) }}</span>
                  <span>{{ formatPrice(priceRange[1]) }}</span>
                </div>
              </div>
            </div>

            <div class="mb-6">
              <h3 class="font-semibold text-gray-700 mb-3">Car Type</h3>
              <div class="space-y-2">
                <label v-for="type in carTypes" :key="type" class="flex items-center gap-2 cursor-pointer">
                  <input type="checkbox" v-model="typeFilter" :value="type"
                    class="form-checkbox text-primary focus:ring-primary rounded" />
                  <span class="text-sm">{{ type }}</span>
                </label>
              </div>
            </div>
            
            <div class="mb-6">
              <h3 class="font-semibold text-gray-700 mb-3">Condition</h3>
              <div class="space-y-2">
                <label v-for="condition in carConditions" :key="condition" class="flex items-center gap-2 cursor-pointer">
                  <input type="checkbox" v-model="conditionFilter" :value="condition"
                    class="form-checkbox text-primary focus:ring-primary rounded" />
                  <span class="text-sm">{{ condition }}</span>
                </label>
              </div>
            </div>
            
            <div class="mb-6">
              <h3 class="font-semibold text-gray-700 mb-3">Year</h3>
              <div class="space-y-2 max-h-40 overflow-y-auto">
                <label v-for="year in carYears" :key="year" class="flex items-center gap-2 cursor-pointer">
                  <input type="checkbox" v-model="yearFilter" :value="year"
                    class="form-checkbox text-primary focus:ring-primary rounded" />
                  <span class="text-sm">{{ year }}</span>
                </label>
              </div>
            </div>
            
            <div class="mb-6">
              <h3 class="font-semibold text-gray-700 mb-3">Transmission</h3>
              <div class="space-y-2">
                <label v-for="transmission in carTransmissions" :key="transmission" class="flex items-center gap-2 cursor-pointer">
                  <input type="checkbox" v-model="transmissionFilter" :value="transmission"
                    class="form-checkbox text-primary focus:ring-primary rounded" />
                  <span class="text-sm">{{ transmission }}</span>
                </label>
              </div>
            </div>
            
            <div class="mb-6">
              <h3 class="font-semibold text-gray-700 mb-3">Fuel Type</h3>
              <div class="space-y-2">
                <label v-for="fuelType in carFuelTypes" :key="fuelType" class="flex items-center gap-2 cursor-pointer">
                  <input type="checkbox" v-model="fuelTypeFilter" :value="fuelType"
                    class="form-checkbox text-primary focus:ring-primary rounded" />
                  <span class="text-sm">{{ fuelType }}</span>
                </label>
              </div>
            </div>
          </div>
          
          <div class="bg-gradient-to-br from-primary to-secondary p-4 rounded-lg shadow-sm text-white">
            <h3 class="font-bold text-lg mb-2">Special Offers</h3>
            <p class="text-sm mb-3">Limited time deals on selected vehicles</p>
            <button class="bg-white text-primary font-medium text-sm px-3 py-1.5 rounded-lg hover:bg-gray-100 transition-colors">
              View Offers
            </button>
          </div>
        </aside>

        <transition name="slide">
          <div v-if="isSidebarOpen" class="fixed inset-0 z-50 bg-black bg-opacity-50 flex md:hidden">
            <div class="w-4/5 max-w-sm bg-white h-full overflow-y-auto" @click.stop>
              <div class="p-4 border-b border-gray-200 flex justify-between items-center">
                <h2 class="text-lg font-bold text-gray-800">Filters</h2>
                <button @click="isSidebarOpen = false">
                  <Icon icon="mdi:close" class="h-6 w-6 text-gray-500" />
                </button>
              </div>
              <div class="p-4 space-y-6">
                <div>
                  <h3 class="font-semibold text-gray-700 mb-3">Price Range</h3>
                  <div class="px-2">
                    <input 
                      type="range" 
                      v-model="priceRange[0]" 
                      :min="minPrice" 
                      :max="maxPrice"
                      class="w-full accent-red-500 mb-2" 
                    />
                    <input 
                      type="range" 
                      v-model="priceRange[1]" 
                      :min="minPrice" 
                      :max="maxPrice"
                      class="w-full accent-red-500" 
                    />
                    <div class="flex justify-between mt-2 text-sm text-gray-600">
                      <span>{{ formatPrice(priceRange[0]) }}</span>
                      <span>{{ formatPrice(priceRange[1]) }}</span>
                    </div>
                  </div>
                </div>

                <div>
                  <h3 class="font-semibold text-gray-700 mb-3">Car Type</h3>
                  <div class="space-y-2">
                    <label v-for="type in carTypes" :key="type" class="flex items-center gap-2 cursor-pointer">
                      <input type="checkbox" v-model="typeFilter" :value="type"
                        class="form-checkbox text-primary focus:ring-primary rounded" />
                      <span class="text-sm">{{ type }}</span>
                    </label>
                  </div>
                </div>
                <div>
                  <h3 class="font-semibold text-gray-700 mb-3">Condition</h3>
                  <div class="space-y-2">
                    <label v-for="condition in carConditions" :key="condition" class="flex items-center gap-2 cursor-pointer">
                      <input type="checkbox" v-model="conditionFilter" :value="condition"
                        class="form-checkbox text-primary focus:ring-primary rounded" />
                      <span class="text-sm">{{ condition }}</span>
                    </label>
                  </div>
                </div>

                <div>
                  <h3 class="font-semibold text-gray-700 mb-3">Year</h3>
                  <div class="space-y-2 max-h-40 overflow-y-auto">
                    <label v-for="year in carYears" :key="year" class="flex items-center gap-2 cursor-pointer">
                      <input type="checkbox" v-model="yearFilter" :value="year"
                        class="form-checkbox text-primary focus:ring-primary rounded" />
                      <span class="text-sm">{{ year }}</span>
                    </label>
                  </div>
                </div>

                <div>
                  <h3 class="font-semibold text-gray-700 mb-3">Transmission</h3>
                  <div class="space-y-2">
                    <label v-for="transmission in carTransmissions" :key="transmission" class="flex items-center gap-2 cursor-pointer">
                      <input type="checkbox" v-model="transmissionFilter" :value="transmission"
                        class="form-checkbox text-primary focus:ring-primary rounded" />
                      <span class="text-sm">{{ transmission }}</span>
                    </label>
                  </div>
                </div>
                <div>
                  <h3 class="font-semibold text-gray-700 mb-3">Fuel Type</h3>
                  <div class="space-y-2">
                    <label v-for="fuelType in carFuelTypes" :key="fuelType" class="flex items-center gap-2 cursor-pointer">
                      <input type="checkbox" v-model="fuelTypeFilter" :value="fuelType"
                        class="form-checkbox text-primary focus:ring-primary rounded" />
                      <span class="text-sm">{{ fuelType }}</span>
                    </label>
                  </div>
                </div>
              </div>

              <div class="p-4 border-t border-gray-200 flex justify-between">
                <button @click="resetFilters" class="text-primary text-sm font-medium hover:underline">
                  Reset
                </button>
                <button @click="isSidebarOpen = false"
                  class="bg-primary text-white px-4 py-2 rounded-lg text-sm font-medium">
                  Apply Filters
                </button>
              </div>
            </div>
          </div>
        </transition>

        <div class="flex-1">
          <div class="flex justify-between items-center mb-6">
            <div>
              <h2 class="text-xl md:text-2xl font-bold text-gray-900">Available Vehicles</h2>
              <p class="text-sm text-gray-500">Check all the available vehicles here</p>
            </div>
          </div>
          
          <div v-if="filteredCars.length === 0" class="bg-white rounded-lg p-8 text-center">
            <Icon icon="mdi:car-off" class="h-16 w-16 text-gray-400 mx-auto mb-4" />
            <h3 class="text-lg font-medium text-gray-900 mb-1">No vehicles found</h3>
            <p class="text-sm text-gray-500 mb-4">Try adjusting your filters to find what you're looking for.</p>
            <button @click="resetFilters" class="text-primary text-sm font-medium hover:underline">
              Reset all filters
            </button>
          </div>
          
          <div v-else-if="viewMode === 'grid'" class="grid grid-cols-1 md:grid-cols-2 gap-6">
        <CarCard
          v-for="car in cars.slice(0, visibleCars)"
          :key="car.id"
          :car="car"
          class="w-full transform hover:scale-105 transition-transform duration-300"
        />
      
          </div>
          
          <div v-else class="space-y-6">
            <div
              v-for="(car, index) in filteredCars.slice(0, visibleCars)"
              :key="car.id"
              class="bg-white rounded-2xl shadow-lg overflow-hidden transition-all duration-300 hover:shadow-xl border border-gray-100 flex flex-col md:flex-row hover:-translate-y-1"
            >
              <div class="relative w-full md:w-1/3 h-56 md:h-auto">
                <img
                  :src="car.image"
                  :alt="car.name"
                  class="w-full h-full object-cover"
                  loading="lazy"
                />
                <div v-if="car.condition"
                  class="absolute top-4 left-4 px-3 py-1 text-white bg-gradient-to-t from-primary to-secondary text-xs font-semibold rounded-full shadow-md"          
                >
                  {{ car.condition }}
                </div>
                <div class="absolute bottom-4 right-4 bg-black/70 text-white text-xs px-2 py-1 rounded">
                  {{ car.year }}
                </div>
              </div>
              <div class="flex-1 p-6 flex flex-col">
                <div class="flex justify-between items-start mb-4">
                  <div>
                    <span class="px-3 py-1 bg-primary/10 text-primary text-xs font-semibold rounded-full">
                      {{ car.type }}
                    </span>
                    <h3 class="text-xl font-bold text-gray-900 mt-2">
                      {{ car.name }}
                    </h3>
                    <p class="text-sm text-gray-500 mt-1">{{ car.make }}</p>
                  </div>
                  <div class="text-right">
                    <div class="text-lg font-bold text-primary">$ {{ formatPrice(car.price) }}</div>
                    <button class="text-gray-400 hover:text-red-500 transition-colors p-1 mt-1">
                      <Icon icon="heroicons:heart" class="w-5 h-5" />
                    </button>
                  </div>
                </div>
                
                <div class="grid grid-cols-2 md:grid-cols-3 gap-3 mb-6">
                  <div
                    class="flex items-center text-start gap-2 p-3 bg-gray-50 rounded-xl transition-colors hover:bg-primary/5"
                  >
                    <div class="p-2 bg-primary/10 rounded-lg">
                      <Icon icon="line-md:calendar" class="w-4 h-4 text-primary" />
                    </div>
                    <div>
                      <div class="text-xs text-gray-500 mb-1">Year</div>
                      <div class="text-sm font-semibold text-gray-900">
                        {{ car.year }}
                      </div>
                    </div>
                  </div>

                  <div
                    class="flex items-center text-start gap-2 p-3 bg-gray-50 rounded-xl transition-colors hover:bg-primary/5"
                  >
                    <div class="p-2 bg-primary/10 rounded-lg">
                      <Icon icon="line-md:speedometer-loop" class="w-4 h-4 text-primary" />
                    </div>
                    <div>
                      <div class="text-xs text-gray-500 mb-1">Mileage</div>
                      <div class="text-sm font-semibold text-gray-900">{{ car.mileage }}</div>
                    </div>
                  </div>

                  <div
                    class="flex items-center text-start gap-2 p-3 bg-gray-50 rounded-xl transition-colors hover:bg-primary/5"
                  >
                    <div class="p-2 bg-primary/10 rounded-lg">
                      <Icon icon="mdi:gas-station" class="w-4 h-4 text-primary" />
                    </div>
                    <div>
                      <div class="text-xs text-gray-500 mb-1">Fuel</div>
                      <div class="text-sm font-semibold text-gray-900">{{ car.fuelType }}</div>
                    </div>
                  </div>

                  <div
                    class="flex items-center text-start gap-2 p-3 bg-gray-50 rounded-xl transition-colors hover:bg-primary/5"
                  >
                    <div class="p-2 bg-primary/10 rounded-lg">
                      <Icon icon="mdi:car-shift-pattern" class="w-4 h-4 text-primary" />
                    </div>
                    <div>
                      <div class="text-xs text-gray-500 mb-1">Transmission</div>
                      <div class="text-sm font-semibold text-gray-900">{{ car.transmission }}</div>
                    </div>
                  </div>

                  <div
                    class="flex items-center text-start gap-2 p-3 bg-gray-50 rounded-xl transition-colors hover:bg-primary/5"
                  >
                    <div class="p-2 bg-primary/10 rounded-lg">
                      <Icon icon="mdi:engine" class="w-4 h-4 text-primary" />
                    </div>
                    <div>
                      <div class="text-xs text-gray-500 mb-1">Engine</div>
                      <div class="text-sm font-semibold text-gray-900">{{ car.engine }}</div>
                    </div>
                  </div>
                </div>
                
                <div class="mt-auto flex justify-between items-center">
                  <div class="flex gap-2">
                    <button class="px-4 py-2 border border-gray-300 text-gray-700 font-medium rounded-lg hover:bg-gray-50 transition-colors">
                      Compare
                    </button>
                    <button 
                      @click="viewCarDetails(car)"
                      class="flex items-center bg-gradient-to-t from-primary to-secondary text-white font-semibold text-sm px-4 py-2 rounded-lg transition-all duration-300 hover:shadow-lg hover:translate-x-1"
                    >
                      View Details
                      <Icon
                        icon="heroicons:arrow-long-right"
                        class="w-5 h-5 ml-2 transition-transform hover:translate-x-1"
                      />
                    </button>
                  </div>
                </div>
              </div>
            </div>
          </div>
          
          <div v-if="visibleCars < filteredCars.length" class="flex justify-center mt-8">
            <button 
              @click="showMore"
              class="px-6 py-3 bg-gradient-to-t from-primary to-secondary text-white font-semibold rounded-lg shadow-md hover:shadow-lg transition-all duration-300 hover:-translate-y-1"
            >
              Show More Vehicles
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.slide-enter-active,
.slide-leave-active {
  transition: transform 0.3s ease;
}

.slide-enter-from,
.slide-leave-to {
  transform: translateX(-100%);
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

input[type="range"] {
  -webkit-appearance: none;
  height: 4px;
  border-radius: 2px;
}

input[type="range"]::-webkit-slider-thumb {
  -webkit-appearance: none;
  width: 16px;
  height: 16px;
  background: #3b82f6;
  border-radius: 50%;
  cursor: pointer;
}

/* Animations */
@keyframes pulse-slow {
  0%, 100% { opacity: 0.5; }
  50% { opacity: 0.8; }
}

.animate-pulse-slow {
  animation: pulse-slow 4s cubic-bezier(0.4, 0, 0.6, 1) infinite;
}

.delay-1000 {
  animation-delay: 1000ms;
}

.delay-500 {
  animation-delay: 500ms;
}
</style>