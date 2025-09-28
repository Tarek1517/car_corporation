<script setup>
import { Icon } from "@iconify/vue";
import { ref } from "vue";
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
    {
        id: 4,
        type: "SUV",
        name: "Corolla Cross",
        year: 2020,
        make: "Toyota",
        image: "/images/crossred.jpeg",
        price: "$26,800",
        mileage: "30,120 mi",
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
    <section
        class="w-full relative overflow-hidden py-2 md:py-6 bg-gradient-to-br from-slate-50 via-white to-slate-100">
        <div
            class="absolute top-0 right-0 w-96 h-96 bg-primary/10 rounded-full -translate-y-1/3 translate-x-1/3 blur-3xl animate-pulse-slow">
        </div>
        <div
            class="absolute bottom-0 left-0 w-[32rem] h-[32rem] bg-secondary/10 rounded-full translate-y-1/3 -translate-x-1/3 blur-3xl animate-pulse-slow delay-1000">
        </div>
        <div
            class="absolute top-1/2 left-1/4 w-64 h-64 bg-primary/5 rounded-full blur-3xl animate-pulse-slow delay-500">
        </div>
        <div class="absolute inset-0 opacity-[0.03] bg-grid-pattern"></div>
        <div class="relative z-10">
            <section class="relative">
                <div class="relative h-[500px] md:h-[600px] w-full overflow-hidden">
                    <img src="../../public/images/car-import.jpg" alt="Our Story Background"
                        class="w-full h-full object-cover" />
                </div>
                <div class="absolute inset-0 bg-black/50"></div>
                <div class="absolute inset-0 flex flex-col items-center justify-center text-center px-4 z-10">
                    <h2 class="text-5xl md:text-6xl font-bold text-white drop-shadow-lg mb-4">
                        Car
                        <span
                            class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary drop-shadow">
                            Import
                        </span>
                    </h2>
                    <p class="text-lg md:text-xl text-gray-200 max-w-2xl">
                        Explore our state-of-the-art import across Bangladesh — where
                        innovation meets elegance and every detail is crafted for an exceptional experience.
                    </p>
                </div>
            </section>
        </div>

        <div class="relative z-10 text-center max-w-7xl mx-auto mt-12">
            <h3 class="text-3xl md:text-4xl font-bold text-gray-900">
                What <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">We Do</span>
            </h3>
            <p class="text-gray-600 mt-3 text-base md:text-lg">
                From consultation to final delivery, we make your car import journey smooth and reliable.
            </p>
        </div>
        <div
            class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 md:gap-8 max-w-7xl mx-auto px-6 relative z-10 py-12">
            <div
                class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-secondary/20 hover:-translate-y-2 relative overflow-hidden">
                <div
                    class="absolute top-0 right-0 w-28 h-28 bg-secondary/5 rounded-bl-full transition-all duration-500 group-hover:bg-secondary/10">
                </div>
                <div class="flex justify-start mb-5 relative z-10">
                    <div
                        class="p-3 bg-gradient-to-br from-secondary/10 to-secondary/5 rounded-xl transition-colors duration-500 group-hover:from-secondary/15 group-hover:to-secondary/10 shadow-sm">
                        <Icon icon="mdi:message-processing-outline" class="w-7 h-7 text-secondary" />
                    </div>
                </div>
                <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
                    Consultation
                </h3>
                <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
                    Buy directly from Japan's top auto auctions with ease and confidence through our seamless import
                    service.
                </p>
            </div>
            <div
                class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-secondary/20 hover:-translate-y-2 relative overflow-hidden">
                <div
                    class="absolute top-0 right-0 w-28 h-28 bg-secondary/5 rounded-bl-full transition-all duration-500 group-hover:bg-secondary/10">
                </div>
                <div class="flex justify-start mb-5 relative z-10">
                    <div
                        class="p-3 bg-gradient-to-br from-secondary/10 to-secondary/5 rounded-xl transition-colors duration-500 group-hover:from-secondary/15 group-hover:to-secondary/10 shadow-sm">
                        <Icon icon="mdi:wallet" class="w-7 h-7 text-secondary" />
                    </div>
                </div>
                <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
                    Purchased
                </h3>
                <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
                    Buy directly from Japan's top auto auctions with ease and confidence through our seamless import
                    service.
                </p>
            </div>
            <div
                class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-primary/20 hover:-translate-y-2 relative overflow-hidden">
                <div
                    class="absolute top-0 right-0 w-28 h-28 bg-primary/5 rounded-bl-full transition-all duration-500 group-hover:bg-primary/10">
                </div>
                <div class="flex justify-start mb-5 relative z-10">
                    <div
                        class="p-3 bg-gradient-to-br from-primary/10 to-primary/5 rounded-xl transition-colors duration-500 group-hover:from-primary/15 group-hover:to-primary/10 shadow-sm">
                        <Icon icon="mdi:credit-card-refund" class="w-7 h-7 text-primary" />
                    </div>
                </div>
                <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
                    Funding
                </h3>
                <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
                    All cars are inspected and verified for quality and condition before auction, ensuring a trusted
                    buying experience.
                </p>
            </div>
            <div
                class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-primary/20 hover:-translate-y-2 relative overflow-hidden">
                <div
                    class="absolute top-0 right-0 w-28 h-28 bg-primary/5 rounded-bl-full transition-all duration-500 group-hover:bg-primary/10">
                </div>
                <div class="flex justify-start mb-5 relative z-10">
                    <div
                        class="p-3 bg-gradient-to-br from-primary/10 to-primary/5 rounded-xl transition-colors duration-500 group-hover:from-primary/15 group-hover:to-primary/10 shadow-sm">
                        <Icon icon="mdi:transportation" class="w-7 h-7 text-primary" />
                    </div>
                </div>
                <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
                    Transportation
                </h3>
                <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
                    All cars are inspected and verified for quality and condition before auction, ensuring a trusted
                    buying experience.
                </p>
            </div>
        </div>
        <div class="relative z-10 text-center max-w-2xl mx-auto mt-12 mb-8">
            <h3 class="text-xl md:text-2xl font-bold text-gray-900">
                Choose <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">The
                    Desired Car</span>
            </h3>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 mb-16 max-w-7xl mx-auto px-6 relative z-10">
            <div v-for="car in cars.slice(0, visibleCars)" :key="car.id"
                class="bg-white rounded-2xl overflow-hidden shadow-lg hover:shadow-2xl transition-all duration-300 transform hover:-translate-y-2 group">
                <div class="relative overflow-hidden h-56">
                    <img :src="car.image" :alt="car.name"
                        class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500">
                    <div class="absolute top-4 right-4">
                        <button class="p-2 bg-white/90 rounded-full shadow-md hover:bg-white transition-colors">
                            <Icon icon="mdi:heart-outline" class="w-5 h-5 text-gray-700" />
                        </button>
                    </div>
                    <div class="absolute bottom-4 left-4">
                        <span class="px-3 py-1 bg-black/70 text-white text-xs font-semibold rounded-full">{{ car.type}}</span>
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
                        <button
                            class="px-4 py-2 bg-gradient-to-r from-primary to-secondary text-white rounded-lg text-sm font-semibold hover:shadow-md transition-shadow">
                            Buy Now
                        </button>
                    </div>
                </div>
            </div>
        </div>
        <div class="relative z-10 text-center max-w-7xl mx-auto mt-12">
            <h3 class="text-xl md:text-2xl font-bold text-gray-900">
                Additional <span
                    class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">Services</span>
            </h3>
        </div>
        <div
            class="grid grid-cols-1 md:grid-cols-1 lg:grid-cols-3 gap-6 md:gap-8 max-w-7xl mx-auto px-6 relative z-10 py-12">
            <div
                class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-secondary/20 hover:-translate-y-2 relative overflow-hidden">
                <div
                    class="absolute top-0 right-0 w-28 h-28 bg-secondary/5 rounded-bl-full transition-all duration-500 group-hover:bg-secondary/10">
                </div>
                <div class="flex justify-start mb-5 relative z-10">
                    <div
                        class="p-3 bg-gradient-to-br from-secondary/10 to-secondary/5 rounded-xl transition-colors duration-500 group-hover:from-secondary/15 group-hover:to-secondary/10 shadow-sm">
                        <Icon icon="mdi:truck" class="w-7 h-7 text-secondary" />
                    </div>
                </div>
                <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
                    Evacuator Service
                </h3>
                <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
                    Buy directly from Japan's top auto auctions with ease and confidence through our seamless import
                    service.
                </p>
            </div>
            <div
                class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-secondary/20 hover:-translate-y-2 relative overflow-hidden">
                <div
                    class="absolute top-0 right-0 w-28 h-28 bg-secondary/5 rounded-bl-full transition-all duration-500 group-hover:bg-secondary/10">
                </div>
                <div class="flex justify-start mb-5 relative z-10">
                    <div
                        class="p-3 bg-gradient-to-br from-secondary/10 to-secondary/5 rounded-xl transition-colors duration-500 group-hover:from-secondary/15 group-hover:to-secondary/10 shadow-sm">
                        <Icon icon="mdi:user" class="w-7 h-7 text-secondary" />
                    </div>
                </div>
                <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
                    For a dealer registration
                </h3>
                <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
                    Buy directly from Japan's top auto auctions with ease and confidence through our seamless import
                    service.
                </p>
            </div>
            <div
                class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-primary/20 hover:-translate-y-2 relative overflow-hidden">
                <div
                    class="absolute top-0 right-0 w-28 h-28 bg-primary/5 rounded-bl-full transition-all duration-500 group-hover:bg-primary/10">
                </div>
                <div class="flex justify-start mb-5 relative z-10">
                    <div
                        class="p-3 bg-gradient-to-br from-primary/10 to-primary/5 rounded-xl transition-colors duration-500 group-hover:from-primary/15 group-hover:to-primary/10 shadow-sm">
                        <Icon icon="mdi:ship" class="w-7 h-7 text-primary" />
                    </div>
                </div>
                <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
                    Safe transportation
                </h3>
                <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
                    All cars are inspected and verified for quality and condition before auction, ensuring a trusted
                    buying experience.
                </p>
            </div>
        </div>
<section class="py-16 bg-primary max-w-7xl mx-auto mt-12 rounded-3xl relative overflow-hidden">
  <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
    <div class="grid grid-cols-1 lg:grid-cols-2 gap-10 items-center">
      <div class="text-center lg:text-left">
        <h2 class="font-manrope text-4xl md:text-5xl text-white font-bold mb-4">
          Subscribe Newsletter
        </h2>
        <p class="text-gray-100 text-lg max-w-md mx-auto lg:mx-0">
          Stay updated with the latest car import deals, auction updates, and exclusive offers straight to your inbox.
        </p>
      </div>
      <div class="flex items-center justify-center lg:justify-end">
        <form class="flex w-full max-w-md bg-white rounded-lg shadow-lg overflow-hidden">
          <input 
            type="email" 
            name="email" 
            placeholder="Your email address..." 
            class="flex-1 px-5 py-3 text-gray-700 text-sm focus:outline-none placeholder:text-gray-400" 
          />
          <button 
            type="submit" 
            class="bg-gradient-to-r from-primary to-secondary text-white text-sm font-semibold px-6 py-3 hover:opacity-90 transition-all"
          >
            Subscribe
          </button>
        </form>
      </div>

    </div>
  </div>
</section>


    </section>
</template>