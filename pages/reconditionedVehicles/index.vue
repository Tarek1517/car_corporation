<script setup>
import { Icon } from "@iconify/vue";
import { ref, computed } from "vue";
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/pagination";
import { Autoplay } from "swiper/modules";
const heroImages = [
    {
        id: 1,
        src: "/images/civik.png",
        alt: "Honda Civic",
        title: "Premium Sedans",
        description: "Experience comfort and efficiency"
    },
    {
        id: 2,
        src: "/images/cross 1.jpeg",
        alt: "Toyota Corolla Cross",
        title: "Versatile SUVs",
        description: "Perfect for family adventures"
    },
    {
        id: 3,
        src: "/images/crv-new-web.png",
        alt: "Toyota CR-V",
        title: "Reliable Crossovers",
        description: "Built for all terrains"
    },
];

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
        condition: "USED",
        fuel: "Hybrid",
        transmission: "Automatic",
        features: ["AWD", "Sunroof", "Leather Seats"]
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
        condition: "USED",
        fuel: "Gasoline",
        transmission: "CVT",
        features: ["Safety Sense", "Touchscreen", "Backup Camera"]
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
        condition: "USED",
        fuel: "Hybrid",
        transmission: "Automatic",
        features: ["Panoramic Roof", "JBL Audio", "Heated Seats"]
    },
    {
        id: 4,
        type: "SUV",
        name: "Toyota Cross",
        year: 2021,
        make: "Toyota",
        image: "/images/toyotacorollacross.jpeg",
        price: "$29,500",
        mileage: "15,670 mi",
        condition: "USED",
        fuel: "Gasoline",
        transmission: "CVT",
        features: ["Apple CarPlay", "Lane Assist", "LED Headlights"]
    },
    {
        id: 5,
        type: "SUV",
        name: "Corolla Cross",
        year: 2020,
        make: "Toyota",
        image: "/images/crossred.jpeg",
        price: "$26,800",
        mileage: "30,120 mi",
        condition: "USED",
        fuel: "Gasoline",
        transmission: "Automatic",
        features: ["Bluetooth", "Cruise Control", "Push Start"]
    },
    {
        id: 6,
        type: "Sedan",
        name: "Honda Civic",
        year: 2019,
        make: "Honda",
        image: "/images/civik2.png",
        price: "$23,900",
        mileage: "35,405 mi",
        condition: "USED",
        fuel: "Gasoline",
        transmission: "CVT",
        features: ["Turbo Engine", "Sport Mode", "Touchscreen"]
    },
];
const brands = [
    { name: "honda", logo: "/images/honda.png" },
    { name: "Toyota", logo: "/images/Toyota.png" },
    { name: "Suzuki", logo: "/images/suzuki.png" },
    { name: "Nissan", logo: "/images/Nissan.png" },
    { name: "Volkswagen", logo: "/images/Volkswagen.png" },
    { name: "Mahindra", logo: "/images/Mahindra.png" },
    { name: "Hyundai", logo: "/images/Hyundai.png" },
];
const selectedType = ref('all');
const selectedCondition = ref('all');

const filteredCars = computed(() => {
    return cars.filter(car => {
        const typeMatch = selectedType.value === 'all' || car.type === selectedType.value;
        const conditionMatch = selectedCondition.value === 'all' || car.condition === selectedCondition.value;
        return typeMatch && conditionMatch;
    });
});

const carTypes = computed(() => {
    const types = [...new Set(cars.map(car => car.type))];
    return ['all', ...types];
});

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
            <Swiper :modules="[Autoplay]" :loop="true" :autoplay="{ delay: 4000, disableOnInteraction: false }"
                :navigation="true" class="h-[400px] md:h-[500px] w-full rounded-xl overflow-hidden shadow-2xl">
                <SwiperSlide v-for="img in heroImages" :key="img.id" class="relative">
                    <img :src="img.src" :alt="img.alt" class="w-full h-full object-cover" />
                    <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-black/40 to-transparent"></div>
                    <div class="absolute bottom-0 left-0 right-0 p-6 md:p-10 text-white">
                        <div class="max-w-4xl mx-auto">
                            <h2 class="text-3xl md:text-5xl font-bold mb-2">{{ img.title }}</h2>
                            <p class="text-lg md:text-xl mb-4 opacity-90">{{ img.description }}</p>
                            <button
                                class="bg-primary hover:bg-primary/90 text-white font-semibold py-2 px-6 rounded-lg transition-all duration-300 transform hover:scale-105 shadow-lg">
                                View Inventory
                            </button>
                        </div>
                    </div>
                </SwiperSlide>
            </Swiper>

            <div class="max-w-7xl mx-auto px-4 py-12">
                <div class="text-center mb-12">
                    <h2 class="text-3xl md:text-4xl font-bold text-gray-800 mb-4">All Used Vehicle List</h2>
                    <p class="text-gray-600 max-w-2xl mx-auto">Discover our carefully selected collection of quality
                        reconditioned vehicles</p>
                </div>
                <div v-if="filteredCars.length > 0" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                    <div v-for="car in filteredCars" :key="car.id"
                        class="bg-white rounded-xl overflow-hidden shadow-lg hover:shadow-2xl transition-all duration-300 transform hover:-translate-y-1">
                        <div class="relative">
                            <img :src="car.image" :alt="car.name" class="w-full h-56 object-cover">
                            <div class="absolute top-4 right-4">
                                <span :class="[
                                    'px-3 py-1 rounded-full text-xs font-bold',
                                    car.condition === 'POPULAR' ? 'bg-yellow-500 text-white' : 'bg-blue-500 text-white'
                                ]">
                                    {{ car.condition }}
                                </span>
                            </div>
                        </div>

                        <div class="p-6">
                            <div class="flex justify-between items-start mb-2">
                                <div>
                                    <h3 class="text-xl font-bold text-gray-800">{{ car.name }}</h3>
                                    <p class="text-gray-600">{{ car.year }} {{ car.make }}</p>
                                </div>
                                <div class="text-right">
                                    <p class="text-xl font-bold text-primary">{{ car.price }}</p>
                                    <p class="text-sm text-gray-500">{{ car.mileage }}</p>
                                </div>
                            </div>

                            <div class="flex flex-wrap gap-2 mb-4">
                                <span class="bg-gray-100 text-gray-700 text-xs px-2 py-1 rounded">
                                    <Icon icon="mdi:gas-station" class="inline-block mr-1" /> {{ car.fuel }}
                                </span>
                                <span class="bg-gray-100 text-gray-700 text-xs px-2 py-1 rounded">
                                    <Icon icon="mdi:car-shift-pattern" class="inline-block mr-1" /> {{ car.transmission
                                    }}
                                </span>
                                <span class="bg-gray-100 text-gray-700 text-xs px-2 py-1 rounded">
                                    <Icon icon="mdi:tag" class="inline-block mr-1" /> {{ car.type }}
                                </span>
                            </div>

                            <div class="mb-4">
                                <div class="flex flex-wrap gap-1">
                                    <span v-for="(feature, index) in car.features.slice(0, 3)" :key="index"
                                        class="text-xs bg-blue-50 text-blue-700 px-2 py-1 rounded">
                                        {{ feature }}
                                    </span>
                                    <span v-if="car.features.length > 3" class="text-xs text-gray-500">
                                        +{{ car.features.length - 3 }} more
                                    </span>
                                </div>
                            </div>

                            <div class="flex justify-between">
                                <button class="text-primary font-medium hover:text-primary/80 transition-colors">
                                    View Details
                                </button>
                                <button
                                    class="bg-primary hover:bg-primary/90 text-white font-medium py-2 px-4 rounded-lg transition-colors">
                                    Schedule Test Drive
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="mx-auto px-4 md:px-6 max-w-7xl relative z-10">
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                    <div class="text-left">
                        <div class="mb-4 flex items-center">
                            <div class="h-0.5 w-8 bg-primary mr-3"></div>
                            <span class="text-sm font-semibold tracking-wider text-primary uppercase">Quality
                                Reconditioned Cars</span>
                        </div>

                        <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 leading-tight mb-6">
                            Find Your Perfect
                            <span
                                class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">Reconditioned
                                Vehicle</span>
                        </h1>

                        <p class="text-xl text-gray-600 mb-8 max-w-xl">
                            Trusted reconditioned vehicles with complete inspection, repair, and delivery solutions.
                            Affordable, reliable, and ready for the road.
                        </p>

                        <div class="flex flex-wrap gap-6 mb-8">
                            <div class="flex items-center">
                                <div class="bg-primary/10 p-2 rounded-lg mr-3">
                                    <Icon icon="mdi:car-wrench" class="w-6 h-6 text-primary" />
                                </div>
                                <div>
                                    <div class="text-2xl font-bold text-gray-900">5K+</div>
                                    <div class="text-sm text-gray-500">Cars Reconditioned</div>
                                </div>
                            </div>
                            <div class="flex items-center">
                                <div class="bg-primary/10 p-2 rounded-lg mr-3">
                                    <Icon icon="mdi:account-group" class="w-6 h-6 text-primary" />
                                </div>
                                <div>
                                    <div class="text-2xl font-bold text-gray-900">3K+</div>
                                    <div class="text-sm text-gray-500">Happy Customers</div>
                                </div>
                            </div>
                        </div>

                    </div>

                    <div class="relative">
                        <div class="rounded-2xl overflow-hidden shadow-2xl border-8 border-white transform rotate-2">
                            <img src="../../public/images/bannerimage.png" alt="Reconditioned Vehicle"
                                class="w-full h-auto object-cover" />
                        </div>
                        <div
                            class="absolute -top-4 -left-4 bg-white rounded-xl p-4 shadow-lg border border-gray-100 animate-float">
                            <div class="flex items-center">
                                <div class="bg-primary/10 p-2 rounded-lg mr-3">
                                    <Icon icon="mdi:car" class="w-5 h-5 text-primary" />
                                </div>
                                <div>
                                    <div class="font-semibold text-gray-900">Fully Inspected</div>
                                    <div class="text-xs text-gray-500">Quality Verified</div>
                                </div>
                            </div>
                        </div>
                        <div
                            class="absolute -bottom-4 -right-4 bg-white rounded-xl p-4 shadow-lg border border-gray-100 animate-float delay-1000">
                            <div class="flex items-center">
                                <div class="bg-secondary/10 p-2 rounded-lg mr-3">
                                    <Icon icon="mdi:truck-delivery" class="w-5 h-5 text-secondary" />
                                </div>
                                <div>
                                    <div class="font-semibold text-gray-900">Door Delivery</div>
                                    <div class="text-xs text-gray-500">Nationwide</div>
                                </div>
                            </div>
                        </div>
                        <div
                            class="absolute -bottom-6 -right-6 w-40 h-40 bg-gradient-to-r from-primary to-secondary rounded-2xl shadow-lg -z-10">
                        </div>
                    </div>
                </div>
            </div>
            <div class="relative z-10 text-center max-w-7xl mx-auto mt-12">
                <h3 class="text-3xl md:text-4xl font-bold text-gray-900">
                    What <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">We
                        Do</span>
                </h3>
                <p class="text-gray-600 mt-3 text-base md:text-lg">
                    From inspection to delivery, we make your recondition vehicle journey smooth, safe, and reliable.
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
                            <Icon icon="mdi:car-search" class="w-7 h-7 text-secondary" />
                        </div>
                    </div>
                    <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
                        Inspection
                    </h3>
                    <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
                        Detailed inspection of recondition vehicles to ensure top quality and reliability.
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
                            <Icon icon="mdi:handshake-outline" class="w-7 h-7 text-secondary" />
                        </div>
                    </div>
                    <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
                        Purchase
                    </h3>
                    <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
                        Securely purchase verified recondition vehicles with confidence and ease.
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
                            <Icon icon="mdi:cash-multiple" class="w-7 h-7 text-primary" />
                        </div>
                    </div>
                    <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
                        Financing
                    </h3>
                    <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
                        Flexible financing options to help you get your recondition vehicle faster and easier.
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
                            <Icon icon="mdi:truck-delivery-outline" class="w-7 h-7 text-primary" />
                        </div>
                    </div>
                    <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
                        Delivery
                    </h3>
                    <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
                        Safe and timely transportation of your recondition vehicle directly to your location.
                    </p>
                </div>
            </div>
            <div class="w-full py-16 bg-gradient-to-b from-gray-50 via-white to-gray-100">
                <div class="text-center mb-10">
                    <h2 class="text-4xl md:text-5xl font-extrabold text-gray-900 mb-4">
                        Brand
                        <span
                            class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">Collection</span>
                    </h2>
                    <p class="text-lg md:text-xl text-gray-600 max-w-4xl mx-auto">
                        Discover top-quality brands offering exceptional products and innovative
                        designs for every lifestyle.
                    </p>
                </div>
                <div class="container mx-auto px-10">
                    <UCarousel :items="brands" loop auto-scroll :slides-per-view="6" :slide-to-scroll="1"
                        class="overflow-visible" :ui="{ item: 'basis-1/6 p-3' }">
                        <template #default="{ item: brand }">
                            <div
                                class="relative group bg-gradient-to-r from-primary/15 to-secondary/10 rounded-3xl flex flex-col items-center justify-center p-6 transition-all duration-500 hover:scale-105 cursor-pointer border border-gray-100">
                                <div
                                    class="w-24 h-24 md:w-28 md:h-28 rounded-full flex items-center justify-center overflow-hidden mb-4 relative group-hover:scale-110 transition-transform duration-500">
                                    <div
                                        class="absolute inset-0 rounded-full bg-gradient-to-r from-primary to-secondary p-1 animate-spin-slow">
                                        <div class="absolute inset-0.5 rounded-full bg-white"></div>
                                    </div>
                                    <div
                                        class="relative w-full h-full rounded-full bg-white flex items-center justify-center p-3 z-10">
                                        <NuxtImg :src="brand.logo" :alt="brand.name"
                                            class="w-full h-full object-contain transition-transform duration-500 group-hover:scale-110"
                                            loading="lazy" format="webp" quality="90" />
                                    </div>
                                </div>

                                <div class="overflow-hidden h-0 group-hover:h-6 transition-all duration-500">
                                    <span
                                        class="text-sm font-semibold text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary transform translate-y-4 group-hover:translate-y-0 transition-transform duration-500">
                                        {{ brand.name }}
                                    </span>
                                </div>
                            </div>
                        </template>
                    </UCarousel>
                </div>
            </div>
        </div>
    </section>
</template>
<style scoped>
.animate-spin-slow {
    animation: spin 8s linear infinite;
}

.animate-shine {
    animation: shine 2s linear infinite;
}

@keyframes spin {
    from {
        transform: rotate(0deg);
    }

    to {
        transform: rotate(360deg);
    }
}

@keyframes shine {
    0% {
        transform: translateX(-100%) rotate(45deg);
    }

    100% {
        transform: translateX(200%) rotate(45deg);
    }
}
</style>