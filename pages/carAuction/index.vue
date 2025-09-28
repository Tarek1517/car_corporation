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
  <section class="w-full relative overflow-hidden py-2 md:py-6 bg-gradient-to-br from-slate-50 via-white to-slate-100">
    <div class="absolute top-0 right-0 w-96 h-96 bg-primary/10 rounded-full -translate-y-1/3 translate-x-1/3 blur-3xl animate-pulse-slow"></div>
    <div class="absolute bottom-0 left-0 w-[32rem] h-[32rem] bg-secondary/10 rounded-full translate-y-1/3 -translate-x-1/3 blur-3xl animate-pulse-slow delay-1000"></div>
    <div class="absolute top-1/2 left-1/4 w-64 h-64 bg-primary/5 rounded-full blur-3xl animate-pulse-slow delay-500"></div>
    <div class="absolute inset-0 opacity-[0.03] bg-grid-pattern"></div>
    
    <div class="relative z-10">
      <section class="relative">
        <div class="relative h-[500px] md:h-[600px] w-full overflow-hidden">
          <img src="../../public/images/auction2.jpg" alt=""
               class="w-full h-full object-cover brightness-75" />
          <div class="absolute inset-0 bg-gradient-to-r from-black/70 to-black/40"></div>
          
          <div class="absolute inset-0 flex flex-col items-start justify-center px-8 md:px-16 text-left z-10">
            <h2 class="text-5xl md:text-7xl font-bold text-white mb-4 drop-shadow-lg">
              Live
              <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">
                Auction Access
              </span>
            </h2>
            <p class="text-xl md:text-2xl text-white max-w-2xl drop-shadow-md mb-8">
              Where every expense becomes a brushstroke of intention, creating a masterpiece of financial well-being and wealth.
            </p>
            <button class="px-8 py-3 bg-gradient-to-r from-primary to-secondary text-white rounded-xl font-semibold text-lg shadow-lg hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1">
              Join Auction Now
            </button>
          </div>
        </div>
      </section>
      <section class="w-full relative overflow-hidden py-12 md:py-20">
        <div class="mx-auto px-4 md:px-6 max-w-7xl relative z-10">
          <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
            <div class="text-left">
              <div class="mb-4 flex items-center">
                <div class="h-0.5 w-8 bg-primary mr-3"></div>
                <span class="text-sm font-semibold tracking-wider text-primary uppercase">Car Auctions Hub</span>
              </div>

              <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 leading-tight mb-6">
                Bid on Your
                <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">Dream Car</span>
              </h1>

              <p class="text-xl text-gray-600 mb-8 max-w-xl">
                Access exclusive car auctions from top dealers nationwide. Transparent bidding, detailed listings, and
                seamless transactions for every car enthusiast.
              </p>

              <div class="flex flex-wrap gap-6 mb-8">
                <div class="flex items-center">
                  <div class="bg-primary/10 p-2 rounded-lg mr-3">
                    <Icon name="mdi:check-circle" class="w-6 h-6 text-primary" />
                  </div>
                  <div>
                    <div class="text-2xl font-bold text-gray-900">5K+</div>
                    <div class="text-sm text-gray-500">Cars Listed</div>
                  </div>
                </div>
                <div class="flex items-center">
                  <div class="bg-primary/10 p-2 rounded-lg mr-3">
                    <Icon name="mdi:check-circle" class="w-6 h-6 text-primary" />
                  </div>
                  <div>
                    <div class="text-2xl font-bold text-gray-900">100+</div>
                    <div class="text-sm text-gray-500">Daily Auctions</div>
                  </div>
                </div>
              </div>

              <div class="flex flex-wrap gap-4">
                <button class="px-8 py-4 bg-gradient-to-r from-primary to-secondary text-white rounded-xl font-semibold shadow-lg hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1 flex items-center">
                  <span>Start Bidding</span>
                  <Icon name="mdi:arrow-right" class="ml-2 w-5 h-5" />
                </button>
                <button class="px-8 py-4 bg-white text-gray-800 border border-gray-200 rounded-xl font-semibold shadow-lg hover:shadow-xl transition-all duration-300 flex items-center">
                  <span>View Catalog</span>
                  <Icon name="mdi:book-open" class="ml-2 w-5 h-5" />
                </button>
              </div>
            </div>

            <div class="relative">
              <div class="rounded-2xl overflow-hidden shadow-2xl border-8 border-white transform rotate-2">
                <img src="../../public/images/auction.jpg" alt="Car Auction Preview"
                     class="w-full h-auto object-cover" />
              </div>

              <div class="absolute -top-4 -left-4 bg-white rounded-xl p-4 shadow-lg border border-gray-100 animate-float">
                <div class="flex items-center">
                  <div class="bg-primary/10 p-2 rounded-lg mr-3">
                    <Icon name="mdi:gavel" class="w-5 h-5 text-primary" />
                  </div>
                  <div>
                    <div class="font-semibold text-gray-900">Live Bidding</div>
                    <div class="text-xs text-gray-500">Real-time Auctions</div>
                  </div>
                </div>
              </div>

              <div class="absolute -bottom-4 -right-4 bg-white rounded-xl p-4 shadow-lg border border-gray-100 animate-float delay-1000">
                <div class="flex items-center">
                  <div class="bg-secondary/10 p-2 rounded-lg mr-3">
                    <Icon name="mdi:truck-delivery" class="w-5 h-5 text-secondary" />
                  </div>
                  <div>
                    <div class="font-semibold text-gray-900">Home Delivery</div>
                    <div class="text-xs text-gray-500">Nationwide Service</div>
                  </div>
                </div>
              </div>

              <div class="absolute -bottom-6 -right-6 w-40 h-40 bg-gradient-to-r from-primary to-secondary rounded-2xl shadow-lg -z-10"></div>
            </div>
          </div>
        </div>
      </section>
      
      <section class="py-16 relative overflow-hidden">
        <div class="absolute top-0 left-0 w-72 h-72 bg-primary/5 rounded-full -translate-x-1/2 -translate-y-1/2 blur-3xl"></div>
        <div class="absolute bottom-0 right-0 w-96 h-96 bg-secondary/5 rounded-full translate-x-1/3 translate-y-1/3 blur-3xl"></div>
        
        <div class="container mx-auto px-6 relative z-10">
          <div class="text-center mb-16">
            <h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-4">
              Featured <span class="text-primary">Auction</span> Vehicles
            </h2>
            <p class="text-xl text-gray-600 max-w-3xl mx-auto">
              Discover exceptional vehicles up for auction. Each car is thoroughly inspected and comes with a detailed history report.
            </p>
          </div>
          <div class="flex flex-wrap justify-center gap-4 mb-12">
            <button class="px-6 py-3 bg-gradient-to-r from-primary to-secondary text-white rounded-xl font-medium shadow-md transition-all duration-300">
              All Vehicles
            </button>
            <button class="px-6 py-3 bg-white text-gray-700 border border-gray-200 rounded-xl font-medium shadow-md hover:shadow-lg transition-all duration-300">
              SUVs
            </button>
            <button class="px-6 py-3 bg-white text-gray-700 border border-gray-200 rounded-xl font-medium shadow-md hover:shadow-lg transition-all duration-300">
              Sedans
            </button>
            <button class="px-6 py-3 bg-white text-gray-700 border border-gray-200 rounded-xl font-medium shadow-md hover:shadow-lg transition-all duration-300">
              Vans
            </button>
            <button class="px-6 py-3 bg-white text-gray-700 border border-gray-200 rounded-xl font-medium shadow-md hover:shadow-lg transition-all duration-300">
              <Icon name="mdi:filter" class="w-5 h-5 mr-1 inline" />
              Filters
            </button>
          </div>
          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 mb-16">
            <div v-for="car in cars.slice(0, visibleCars)" :key="car.id" 
                 class="bg-white rounded-2xl overflow-hidden shadow-lg hover:shadow-2xl transition-all duration-300 transform hover:-translate-y-2 group">
              <div class="relative overflow-hidden h-56">
                <img :src="car.image" :alt="car.name" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500">
                <div class="absolute top-4 left-4">
                  <span class="px-3 py-1 bg-primary text-white text-xs font-semibold rounded-full">{{ car.condition || 'Certified' }}</span>
                </div>
                <div class="absolute top-4 right-4">
                  <button class="p-2 bg-white/90 rounded-full shadow-md hover:bg-white transition-colors">
                    <Icon name="mdi:heart-outline" class="w-5 h-5 text-gray-700" />
                  </button>
                </div>
                <div class="absolute bottom-4 left-4">
                  <span class="px-3 py-1 bg-black/70 text-white text-xs font-semibold rounded-full">{{ car.type }}</span>
                </div>
              </div>
              
              <div class="p-6">
                <div class="flex justify-between items-start mb-2">
                  <h3 class="text-xl font-bold text-gray-900">{{ car.name }}</h3>
                  <span class="text-xs text-gray-500">{{ car.year }}</span>
                </div>
                <p class="text-gray-600 mb-4">{{ car.make }} • {{ car.mileage }}</p>
                
                <div class="flex justify-between items-center">
                  <span class="text-2xl font-bold text-primary">{{ car.price }}</span>
                  <button class="px-4 py-2 bg-gradient-to-r from-primary to-secondary text-white rounded-lg text-sm font-semibold hover:shadow-md transition-shadow">
                    Bid Now
                  </button>
                </div>
              </div>
              
              <div class="px-6 pb-4 opacity-0 group-hover:opacity-100 transition-opacity duration-300">
                <div class="flex justify-between border-t border-gray-100 pt-4">
                  <button class="flex items-center text-sm text-gray-600 hover:text-primary">
                    <Icon name="mdi:eye" class="w-4 h-4 mr-1" />
                    Preview
                  </button>
                  <button class="flex items-center text-sm text-gray-600 hover:text-primary">
                    <Icon name="mdi:chart-bar" class="w-4 h-4 mr-1" />
                    History
                  </button>
                  <button class="flex items-center text-sm text-gray-600 hover:text-primary">
                    <Icon name="mdi:share" class="w-4 h-4 mr-1" />
                    Share
                  </button>
                </div>
              </div>
            </div>
          </div>
          
          <div class="text-center" v-if="visibleCars < cars.length">
            <button @click="showMore" class="px-8 py-3 bg-white text-primary border border-primary rounded-xl font-semibold shadow-md hover:bg-primary hover:text-white transition-all duration-300">
              Load More Vehicles
            </button>
          </div>
        </div>
      </section>
      <section class="py-16 bg-gradient-to-r from-primary/5 to-secondary/5 rounded-3xl mx-4 mb-12">
        <div class="container mx-auto px-6">
          <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
            <div class="text-center">
              <div class="text-5xl font-bold text-primary mb-2">200+</div>
              <div class="text-xl font-semibold text-gray-800">Daily Auctions</div>
              <p class="text-gray-600 mt-2">New opportunities every day</p>
            </div>
            <div class="text-center">
              <div class="text-5xl font-bold text-primary mb-2">95%</div>
              <div class="text-xl font-semibold text-gray-800">Satisfaction Rate</div>
              <p class="text-gray-600 mt-2">Happy customers nationwide</p>
            </div>
            <div class="text-center">
              <div class="text-5xl font-bold text-primary mb-2">24/7</div>
              <div class="text-xl font-semibold text-gray-800">Support</div>
              <p class="text-gray-600 mt-2">Our team is always available</p>
            </div>
          </div>
        </div>
      </section>
              <div class="relative z-10 text-center max-w-2xl mx-auto mt-12 mb-8">
            <h3 class="text-3xl md:text-4xl font-bold text-gray-900">
                Services <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">We Provides</span>
            </h3>
            <p class="text-gray-600">
                Explore our comprehensive services designed to enhance your car buying and selling experience.
            </p>
        </div>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 md:gap-8 max-w-6xl mx-auto px-6 relative z-10">

  <div
    class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-primary/20 hover:-translate-y-2 relative overflow-hidden">
    <div
      class="absolute top-0 right-0 w-28 h-28 bg-primary/5 rounded-bl-full transition-all duration-500 group-hover:bg-primary/10">
    </div>
    <div class="flex justify-start mb-5 relative z-10">
      <div
        class="p-3 bg-gradient-to-br from-primary/10 to-primary/5 rounded-xl transition-colors duration-500 group-hover:from-primary/15 group-hover:to-primary/10 shadow-sm">
        <Icon name="mdi:gavel" class="w-7 h-7 text-primary" />
      </div>
    </div>
    <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
      Live Auctions
    </h3>
    <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
      Participate in real-time car auctions with transparent bidding and instant updates on your favorite vehicles.
    </p>
    <div class="flex items-center relative z-10">
      <div
        class="w-8 h-8 rounded-full bg-primary/5 flex items-center justify-center transition-colors duration-300 group-hover:bg-primary/10">
        <Icon name="mdi:arrow-right" class="text-primary transition-all duration-500 transform group-hover:translate-x-1" />
      </div>
      <span class="text-primary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0">Join Auction</span>
    </div>
  </div>

  <!-- Card 2: Nationwide Delivery -->
  <div
    class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-secondary/20 hover:-translate-y-2 relative overflow-hidden">
    <div
      class="absolute top-0 right-0 w-28 h-28 bg-secondary/5 rounded-bl-full transition-all duration-500 group-hover:bg-secondary/10">
    </div>
    <div class="flex justify-start mb-5 relative z-10">
      <div
        class="p-3 bg-gradient-to-br from-secondary/10 to-secondary/5 rounded-xl transition-colors duration-500 group-hover:from-secondary/15 group-hover:to-secondary/10 shadow-sm">
        <Icon name="mdi:truck-delivery" class="w-7 h-7 text-secondary" />
      </div>
    </div>
    <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
      Nationwide Delivery
    </h3>
    <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
      Get your purchased vehicles delivered safely to your location anywhere in the country with full tracking support.
    </p>
    <div class="flex items-center relative z-10">
      <div
        class="w-8 h-8 rounded-full bg-secondary/5 flex items-center justify-center transition-colors duration-300 group-hover:bg-secondary/10">
        <Icon name="mdi:arrow-right" class="text-secondary transition-all duration-500 transform group-hover:translate-x-1" />
      </div>
      <span class="text-secondary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0">Views Delivery</span>
    </div>
  </div>

  <!-- Card 3: Verified Cars -->
  <div
    class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-primary/20 hover:-translate-y-2 relative overflow-hidden">
    <div
      class="absolute top-0 right-0 w-28 h-28 bg-primary/5 rounded-bl-full transition-all duration-500 group-hover:bg-primary/10">
    </div>
    <div class="flex justify-start mb-5 relative z-10">
      <div
        class="p-3 bg-gradient-to-br from-primary/10 to-primary/5 rounded-xl transition-colors duration-500 group-hover:from-primary/15 group-hover:to-primary/10 shadow-sm">
        <Icon name="mdi:check" class="w-7 h-7 text-primary" />
      </div>
    </div>
    <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
      Verified Cars
    </h3>
    <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
      All cars are inspected and verified for quality and condition before auction, ensuring a trusted buying experience.
    </p>
    <div class="flex items-center relative z-10">
      <div
        class="w-8 h-8 rounded-full bg-primary/5 flex items-center justify-center transition-colors duration-300 group-hover:bg-primary/10">
        <Icon name="mdi:arrow-right" class="text-primary transition-all duration-500 transform group-hover:translate-x-1" />
      </div>
      <span class="text-primary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0">View Cars</span>
    </div>
  </div>

</div>

    </div>
  </section>
</template>

<style>
.animate-float {
  animation: float 6s ease-in-out infinite;
}

@keyframes float {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-10px);
  }
}

.animate-pulse-slow {
  animation: pulse 4s cubic-bezier(0.4, 0, 0.6, 1) infinite;
}

@keyframes pulse {
  0%, 100% {
    opacity: 0.5;
  }
  50% {
    opacity: 0.8;
  }
}

.bg-grid-pattern {
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 32 32' width='32' height='32' fill='none' stroke='rgb(15 23 42 / 0.04)'%3e%3cpath d='M0 .5H31.5V32'/%3e%3c/svg%3e");
}
</style>