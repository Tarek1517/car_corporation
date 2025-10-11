<script setup>
import { ref, computed } from "vue";
import { Icon } from "@iconify/vue";

const form = ref({
  search: "",
});

const cars = ref([
  {
    picture: '/images/brv_slider_new.png',
    stockId: 'AX-2020-001',
    makeModel: 'Toyota Axio Hybrid',
    grade: '4.5',
    chassisCode: 'NKH165-123456',
    year: '2020',
    color: 'Silver',
    colorCode: '#C0C0C0',
    engineCC: '1500',
    fuel: 'Hybrid',
    mileage: '49,998',
    auctionPoint: 'USS Tokyo',
    price: '2,650,000 Taka',
    status: 'Upcoming'
  },
  {
    picture: '/images/city-new-web.png',
    stockId: 'RAV-2020-002',
    makeModel: 'Toyota RAV 4 Non-Hybrid',
    grade: '5',
    chassisCode: 'ACA33-789012',
    year: '2020',
    color: 'black',
    colorCode: '#000000',
    engineCC: '2000',
    fuel: 'Petrol',
    mileage: '38,000',
    auctionPoint: 'USS Osaka',
    price: '6,400,000 Taka',
    status: 'Available'
  },
  {
    picture: '/images/accord-new-web.png',
    stockId: 'PRI-2019-003',
    makeModel: 'Toyota Prius Hybrid',
    grade: '4',
    chassisCode: 'ZVW50-345678',
    year: '2019',
    color: 'Blue',
    colorCode: '#1E90FF',
    engineCC: '1800',
    fuel: 'Hybrid',
    mileage: '42,500',
    auctionPoint: 'TAA Kobe',
    price: '3,200,000 Taka',
    status: 'Available'
  },
  {
    picture: '/images/nissan (2).png',
    stockId: 'VOX-2021-004',
    makeModel: 'Nissan Note',
    grade: '4.5',
    chassisCode: 'HE12-901234',
    year: '2021',
    color: 'Red',
    colorCode: '#FF0000',
    engineCC: '1200',
    fuel: 'Hybrid',
    mileage: '18,200',
    auctionPoint: 'JU Fukuoka',
    price: '2,850,000 Taka',
    status: 'Sold'
  },
  {
    picture: '/images/honda-accord.png',
    stockId: 'FIT-2020-005',
    makeModel: 'Honda Fit Hybrid',
    grade: '4',
    chassisCode: 'GK5-567890',
    year: '2020',
    color: 'Black',
    colorCode: '#000000',
    engineCC: '1500',
    fuel: 'Hybrid',
    mileage: '35,700',
    auctionPoint: 'USS Nagoya',
    price: '2,950,000 Taka',
    status: 'Available'
  },
  {
    picture: '/images/car-57.png',
    stockId: 'CRW-2021-011',
    makeModel: 'Toyota Crown Hybrid',
    grade: '4.5',
    chassisCode: 'AZSH21-123456',
    year: '2021',
    color: 'Blue',
    colorCode: '#1E3A8A',
    engineCC: '2500',
    fuel: 'Hybrid',
    mileage: '22,400',
    auctionPoint: 'USS Tokyo',
    price: '7,850,000 Taka',
    status: 'Upcoming'
  },
  {
    picture: '/images/car-yellow.png',
    stockId: 'PRI-2019-022',
    makeModel: 'Toyota Prius Hybrid',
    grade: '4',
    chassisCode: 'ZVW50-334455',
    year: '2019',
    color: 'Yellow',
    colorCode: '#FFD700',
    engineCC: '1800',
    fuel: 'Hybrid',
    mileage: '39,800',
    auctionPoint: 'USS Yokohama',
    price: '3,450,000 Taka',
    status: 'Sold'
  }
]);

const filteredCars = computed(() => {
  if (!form.value.search.trim()) {
    return cars.value;
  }

  const searchTerm = form.value.search.toLowerCase().trim();

  return cars.value.filter(car => {
    return (
      car.makeModel.toLowerCase().includes(searchTerm) ||
      car.stockId.toLowerCase().includes(searchTerm) ||
      car.chassisCode.toLowerCase().includes(searchTerm) ||
      car.year.includes(searchTerm) ||
      car.color.toLowerCase().includes(searchTerm) ||
      car.engineCC.includes(searchTerm) ||
      car.fuel.toLowerCase().includes(searchTerm) ||
      car.mileage.includes(searchTerm) ||
      car.auctionPoint.toLowerCase().includes(searchTerm) ||
      car.price.toLowerCase().includes(searchTerm) ||
      car.status.toLowerCase().includes(searchTerm)
    );
  });
});

const getGradeClass = (grade) => {
  if (grade >= 4.5) return 'bg-green-100 text-green-800';
  if (grade >= 4) return 'bg-blue-100 text-blue-800';
  return 'bg-yellow-100 text-yellow-800';
};

const getStatusClass = (status) => {
  if (status === 'Available') return 'bg-green-100 text-green-800';
  if (status === 'Upcoming') return 'bg-blue-100 text-blue-800';
  if (status === 'Sold') return 'bg-red-100 text-red-800';
  return 'bg-gray-100 text-gray-800';
};


const handleSearch = (event) => {
  event.preventDefault();
};
</script>

<template>
  <section class="w-full relative overflow-hidden py-2 md:py-6 bg-gradient-to-br from-slate-50 via-white to-slate-100">
    <div
      class="absolute top-0 right-0 w-96 h-96 bg-primary/10 rounded-full -translate-y-1/3 translate-x-1/3 blur-3xl animate-pulse-slow">
    </div>
    <div
      class="absolute bottom-0 left-0 w-[32rem] h-[32rem] bg-secondary/10 rounded-full translate-y-1/3 -translate-x-1/3 blur-3xl animate-pulse-slow delay-1000">
    </div>
    <div class="absolute top-1/2 left-1/4 w-64 h-64 bg-primary/5 rounded-full blur-3xl animate-pulse-slow delay-500">
    </div>
    <div class="absolute inset-0 opacity-[0.03] bg-grid-pattern"></div>
    <div class="container mx-auto px-4 relative">
      <div class="text-center">
        <h2 class="text-center text-3xl text-gray-600 font-semibold">Stock List | {{ filteredCars.length }} Cars</h2>
      </div>
      <form @submit="handleSearch" class="flex justify-center py-6 md:py-10">
        <div class="relative w-full max-w-xl flex">
          <Icon icon="mdi:search" class="absolute left-3 top-1/2 transform -translate-y-1/2 w-5 h-5 text-gray-400" />
          <input v-model="form.search" type="text" placeholder="Search with keyword"
            class="w-full pl-10 pr-2 py-2 rounded-l-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-700"
            required />
          <button type="submit"
            class="px-3 py-2 bg-gradient-to-r from-primary to-secondary text-white font-semibold rounded-r-lg shadow-lg hover:shadow-xl transition-all hover:scale-[1.02]">
            Search
          </button>
        </div>
      </form>
      <div class="px-1 py-8">
        <h2 class="text-2xl font-bold text-center mb-8 text-gray-600">Japanese Car Auction Listings</h2>

        <div class="overflow-x-auto bg-white rounded-xl shadow-lg max-w-7xl">
          <table class="min-w-full divide-y divide-gray-200">
            <thead class="bg-gray-50">
              <tr>
                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                  Picture</th>
                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                  Stock ID</th>
                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                  Make Model</th>
                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                  Grade</th>
                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                  Chassis Code</th>
                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                  Year</th>
                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                  Color</th>
                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                  Engine CC</th>
                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                  Fuel</th>
                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                  Mileage</th>
                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                  Auction Point</th>
                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                  Price</th>
                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                  Status</th>
              </tr>
            </thead>
            <tbody class="bg-white divide-y divide-gray-200">
              <tr v-for="(car, index) in filteredCars" :key="index" class="hover:bg-gray-50">
                <td class="px-4 py-4 whitespace-nowrap">
                  <img :src="car.picture" :alt="car.makeModel" class="h-16 w-24 object-cover rounded-md">
                </td>
                <td class="px-4 py-4 whitespace-nowrap text-sm font-medium text-gray-900">
                  <NuxtLink to="/StockList/stock-details">{{ car.stockId }}</NuxtLink>
                </td>
                <td class="px-4 py-4 text-sm text-gray-900">{{ car.makeModel }}</td>
                <td class="px-4 py-4 whitespace-nowrap">
                  <span class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full"
                    :class="getGradeClass(car.grade)">
                    {{ car.grade }}
                  </span>
                </td>
                <td class="px-4 py-4 whitespace-nowrap text-sm text-gray-500">{{ car.chassisCode }}</td>
                <td class="px-4 py-4 whitespace-nowrap text-sm text-gray-500">{{ car.year }}</td>
                <td class="px-4 py-4 whitespace-nowrap text-sm text-gray-500">
                  <span class="inline-block w-4 h-4 rounded-full mr-2"
                    :style="{ backgroundColor: car.colorCode }"></span>
                  {{ car.color }}
                </td>
                <td class="px-4 py-4 whitespace-nowrap text-sm text-gray-500">{{ car.engineCC }}</td>
                <td class="px-4 py-4 whitespace-nowrap text-sm text-gray-500">{{ car.fuel }}</td>
                <td class="px-4 py-4 whitespace-nowrap text-sm text-gray-500">{{ car.mileage }}</td>
                <td class="px-4 py-4 whitespace-nowrap text-sm text-gray-500">{{ car.auctionPoint }}</td>
                <td class="px-4 py-4 whitespace-nowrap text-sm font-semibold text-gray-900">{{ car.price }}</td>
                <td class="px-4 py-4 whitespace-nowrap">
                  <span class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full"
                    :class="getStatusClass(car.status)">
                    {{ car.status }}
                  </span>
                </td>
                <!-- <td class="px-4 py-4 whitespace-nowrap text-sm font-medium">
              <button @click="inquire(car.stockId)" 
                      class="px-3 py-1 bg-blue-600 text-white rounded-md hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-offset-2">
                Inquiry
              </button>
            </td> -->
              </tr>
            </tbody>
          </table>
          <div v-if="filteredCars.length === 0" class="text-center py-8 text-gray-500">
            No cars found matching your search criteria.
          </div>
        </div>
      </div>
    </div>
  </section>
</template>