<script setup>
import { Icon } from '@iconify/vue'
const features = [
    {
        icon: 'mdi:engine-outline',
        title: 'Engine & Transmission',
        text: 'Complete repair and maintenance of engines, gearboxes, and transmission systems to ensure smooth performance.'
    },
    {
        icon: 'mdi:car-brake-alert',
        title: 'Brakes & Suspension',
        text: 'Inspection and servicing of brakes, shocks, and suspension systems for safe and stable driving.'
    },
    {
        icon: 'mdi:car-tire-alert',
        title: 'Tires & Wheels',
        text: 'Tire rotation, balancing, wheel alignment, and replacement for better grip and longer tire life.'
    },
    {
        icon: 'mdi:car-light-high',
        title: 'Lights & Electrical',
        text: 'Diagnosis and repair of headlights, tail lights, battery, alternator, and full electrical systems.'
    },
    {
        icon: 'carbon:smoke',
        title: 'Exhaust & Emissions',
        text: 'Exhaust system repair, catalytic converter service, and emission control to meet environmental standards.'
    },
    {
        icon: 'mdi:airbag',
        title: 'Interior & Safety Features',
        text: 'Maintenance of airbags, seatbelts, dashboards, and comfort features for maximum safety and convenience.'
    },
    {
        icon: 'mdi:car-connected',
        title: 'Computer Diagnostics',
        text: 'Advanced scanning and troubleshooting of engine codes, sensors, and onboard computer systems.'
    }
]
import { Swiper, SwiperSlide } from "swiper/vue";
import { Pagination, Autoplay } from "swiper/modules";
import "swiper/css";
import "swiper/css/pagination";
import { ref } from "vue";
const testimonials = [
    {
        id: 1,
        rating: 4.9,
        text: "Car Corporations BD made the auction process seamless. I got my dream Honda Civic at a great price with their expert bidding assistance.",
        name: "Rahim Khan",
        role: "Satisfied Customer",
        avatar: "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1887&q=80",
    },
    {
        id: 2,
        rating: 5.0,
        text: "The import process was handled perfectly. My Toyota Allion arrived in Bangladesh without any customs issues thanks to their professional team.",
        name: "Fatima Ahmed",
        role: "Business Owner",
        avatar: "https://images.unsplash.com/photo-1544005313-94ddf0286df2?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1888&q=80",
    },
    {
        id: 3,
        rating: 4.8,
        text: "I've imported 5 vehicles through Car Corporations BD. Their auction access and negotiation skills have saved me thousands on each purchase.",
        name: "Tariqul Islam",
        role: "Car Dealer",
        avatar: "https://images.unsplash.com/photo-1552058544-f2b08422138a?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1899&q=80",
    },
    {
        id: 4,
        rating: 4.9,
        text: "The after-sales support exceeded my expectations. They helped with registration and even recommended a trusted mechanic for maintenance.",
        name: "Nusrat Jahan",
        role: "HR Executive",
        avatar: "https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1888&q=80",
    },
];

const faqs = ref([
    {
        question: "What services does Car Corporation provide?",
        answer:
            "We provide car sales (new & used), financing, insurance, after-sales service, and spare parts support.",
        open: false,
    },
    {
        question: "Do you offer car financing options?",
        answer:
            "Yes, we partner with leading banks and financial institutions to provide flexible financing plans for our customers.",
        open: false,
    },
    {
        question: "Can I trade in my old car?",
        answer:
            "Absolutely! We offer trade-in options where you can exchange your old car for a new or used one with fair valuation.",
        open: false,
    },
    {
        question: "Do you provide warranty on used cars?",
        answer:
            "Yes, we provide limited warranty and certified inspection for all our used cars to ensure quality and reliability.",
        open: false,
    },
]);

const toggleFAQ = (index) => {
    faqs.value[index].open = !faqs.value[index].open;
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
            <div class="text-center ">
                <section class="relative bg-gradient-to-br from-slate-50 via-white to-slate-100">
                    <div class="relative h-[500px] md:h-[600px] w-full">
                        <img src="../../public/images/car-Inspect.jpg" alt="Car Insurance Background"
                            class="w-full h-full object-cover" />
                        <div class="absolute inset-0 bg-black/40"></div>
                        <div class="absolute inset-0 flex flex-col items-center justify-center text-center px-4 z-10">
                            <h2 class="text-4xl md:text-5xl font-bold text-white mb-4">
                                Get Your
                                <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">
                                    Car Inspect Today
                                </span>
                            </h2>
                            <p class="text-xl text-white max-w-2xl">
                                Fast, Affordable, and Reliable Car Inspect Plans
                            </p>
                        </div>
                    </div>
                </section>
            </div>
        </div>
        <section class="w-full py-16 bg-white">
            <div class="max-w-6xl mx-auto grid grid-cols-1 md:grid-cols-4 lg:grid-cols-4 px-4">
                <div v-for="(item, index) in features" :key="index"
                    class="text-center px-6 py-10 border border-gray-200">
                    <Icon :icon="item.icon" class="text-red-500 text-5xl mb-4 mx-auto" />
                    <h3 class="font-bold text-gray-700 text-lg mb-2">{{ item.title }}</h3>
                    <p class="text-gray-700 text-sm leading-relaxed">
                        {{ item.text }}
                    </p>
                </div>
            </div>
        </section>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-3 md:gap-8 max-w-6xl mx-auto px-4 py-12">
            <div
                class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-primary/20 hover:-translate-y-2 relative overflow-hidden">
                <div
                    class="absolute top-0 right-0 w-28 h-28 bg-primary/5 rounded-bl-full transition-all duration-500 group-hover:bg-primary/10">
                </div>
                <div class="flex justify-start mb-5 relative z-10">
                    <div
                        class="p-3 bg-gradient-to-br from-primary/10 to-primary/5 rounded-xl transition-colors duration-500 group-hover:from-primary/15 group-hover:to-primary/10 shadow-sm">
                        <Icon icon="mdi:car-info" class="w-7 h-7 text-primary" />
                    </div>
                </div>
                <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
                    General Health Check
                </h3>
                <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
                    Comprehensive multi-point inspection covering engine, brakes, suspension, and electronics for peace
                    of mind.
                </p>
                <div class="flex items-center relative z-10">
                    <div
                        class="w-8 h-8 rounded-full bg-primary/5 flex items-center justify-center transition-colors duration-300 group-hover:bg-primary/10">
                        <Icon icon="mdi:arrow-right"
                            class="text-primary transition-all duration-500 transform group-hover:translate-x-1" />
                    </div>
                    <span
                        class="text-primary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0">Learn
                        more</span>
                </div>
            </div>
            <div
                class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-secondary/20 hover:-translate-y-2 relative overflow-hidden">
                <div
                    class="absolute top-0 right-0 w-28 h-28 bg-secondary/5 rounded-bl-full transition-all duration-500 group-hover:bg-secondary/10">
                </div>
                <div class="flex justify-start mb-5 relative z-10">
                    <div
                        class="p-3 bg-gradient-to-br from-secondary/10 to-secondary/5 rounded-xl transition-colors duration-500 group-hover:from-secondary/15 group-hover:to-secondary/10 shadow-sm">
                        <Icon icon="mdi:clipboard-search" class="w-7 h-7 text-secondary" />
                    </div>
                </div>
                <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
                    Pre-Purchase Inspection
                </h3>
                <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
                    Detailed inspection before buying a vehicle, ensuring no hidden issues and transparent condition
                    reports.
                </p>
                <div class="flex items-center relative z-10">
                    <div
                        class="w-8 h-8 rounded-full bg-secondary/5 flex items-center justify-center transition-colors duration-300 group-hover:bg-secondary/10">
                        <Icon icon="mdi:arrow-right"
                            class="text-secondary transition-all duration-500 transform group-hover:translate-x-1" />
                    </div>
                    <span
                        class="text-secondary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0">Book
                        now</span>
                </div>
            </div>
            <div
                class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-primary/20 hover:-translate-y-2 relative overflow-hidden">
                <div
                    class="absolute top-0 right-0 w-28 h-28 bg-primary/5 rounded-bl-full transition-all duration-500 group-hover:bg-primary/10">
                </div>
                <div class="flex justify-start mb-5 relative z-10">
                    <div
                        class="p-3 bg-gradient-to-br from-primary/10 to-primary/5 rounded-xl transition-colors duration-500 group-hover:from-primary/15 group-hover:to-primary/10 shadow-sm">
                        <Icon icon="mdi:road-variant" class="w-7 h-7 text-primary" />
                    </div>
                </div>
                <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
                    Roadworthiness Inspection
                </h3>
                <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
                    Mandatory checks to ensure your car meets legal and safety standards for road use.
                </p>
                <div class="flex items-center relative z-10">
                    <div
                        class="w-8 h-8 rounded-full bg-primary/5 flex items-center justify-center transition-colors duration-300 group-hover:bg-primary/10">
                        <Icon icon="mdi:arrow-right"
                            class="text-primary transition-all duration-500 transform group-hover:translate-x-1" />
                    </div>
                    <span
                        class="text-primary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0">Check
                        details</span>
                </div>
            </div>
            <div
                class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-secondary/20 hover:-translate-y-2 relative overflow-hidden">
                <div
                    class="absolute top-0 right-0 w-28 h-28 bg-secondary/5 rounded-bl-full transition-all duration-500 group-hover:bg-secondary/10">
                </div>
                <div class="flex justify-start mb-5 relative z-10">
                    <div
                        class="p-3 bg-gradient-to-br from-secondary/10 to-secondary/5 rounded-xl transition-colors duration-500 group-hover:from-secondary/15 group-hover:to-secondary/10 shadow-sm">
                        <Icon icon="mdi:file-document-check" class="w-7 h-7 text-secondary" />
                    </div>
                </div>
                <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
                    Insurance / Loan Inspection
                </h3>
                <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
                    Certified inspection reports for insurance claims, financing, or loan approvals.
                </p>
                <div class="flex items-center relative z-10">
                    <div
                        class="w-8 h-8 rounded-full bg-secondary/5 flex items-center justify-center transition-colors duration-300 group-hover:bg-secondary/10">
                        <Icon icon="mdi:arrow-right"
                            class="text-secondary transition-all duration-500 transform group-hover:translate-x-1" />
                    </div>
                    <span
                        class="text-secondary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0">Get
                        certified</span>
                </div>
            </div>
        </div>
        <section class="py-16 md:py-24 bg-gradient-to-b from-slate-50 to-white">
            <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">

                <div class="mb-16 text-center">
                    <div class="inline-flex items-center justify-center mb-4">
                        <div class="h-0.5 w-8 bg-primary mr-3"></div>
                        <span class="text-sm font-semibold tracking-wider text-primary uppercase">CLIENT
                            TESTIMONIALS</span>
                        <div class="h-0.5 w-8 bg-primary ml-3"></div>
                    </div>
                    <h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-4">What Our Satisfied Clients Say</h2>
                    <p class="text-lg text-gray-600 max-w-2xl mx-auto">
                        Hear from customers who have experienced our premium vehicle auction and import services.
                    </p>
                </div>

                <Swiper :modules="[Pagination, Autoplay]" :slides-per-view="1" :space-between="30" :loop="true"
                    :centered-slides="true" :autoplay="{ delay: 5000, disableOnInteraction: false }"
                    :pagination="{ clickable: true, el: '.testimonial-pagination' }" :breakpoints="{
                        640: {
                            slidesPerView: 1,
                        },
                        768: {
                            slidesPerView: 2,
                        },
                        1024: {
                            slidesPerView: 3,
                        },
                    }" class="pb-16">
                    <SwiperSlide v-for="item in testimonials" :key="item.id">
                        <div
                            class="group bg-white border border-gray-200 rounded-2xl p-6 transition-all duration-500 hover:border-primary/30 hover:shadow-lg h-full flex flex-col">
                            <div class="flex items-center mb-6 gap-1 text-amber-500">
                                <Icon v-for="star in 5" :key="star" icon="mdi:star" class="w-5 h-5" />
                                <span class="text-base font-semibold text-gray-700 ml-2">{{ item.rating }}</span>
                            </div>
                            <p class="text-gray-600 leading-relaxed mb-8 flex-grow group-hover:text-gray-800">
                                "{{ item.text }}"
                            </p>
                            <div class="flex items-center gap-4 border-t border-gray-100 pt-6 mt-auto">
                                <img :src="item.avatar" alt="avatar"
                                    class="rounded-full h-12 w-12 object-cover shadow-sm" />
                                <div>
                                    <h5 class="text-gray-900 font-semibold">{{ item.name }}</h5>
                                    <span class="text-sm text-gray-500">{{ item.role }}</span>
                                </div>
                            </div>
                        </div>
                    </SwiperSlide>
                    <div class="testimonial-pagination flex justify-center mt-10 space-x-2"></div>
                </Swiper>

            </div>
        </section>
        <section class="py-6 bg-white">
            <div class="text-center items-center justify-center py-12">
                <p class="text-md text-gray-400">We’d Love to Hear From You</p>
                <h3 class="text-4xl text-gray-700 text-center">
                    LET'S GET IN TOUCH!
                </h3>
                <div class="flex justify-center items-center py-2">
                    <div class="border-b bg-primary w-20 border-primary border-2"></div>
                    <div class="border-b bg-primary w-10 border-primary border-2"></div>
                </div>
            </div>
            <div class="container mx-auto px-4">
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4">
                    <div
                        class="bg-white p-6 flex flex-col items-center text-center shadow-sm border border-gray-100 hover:shadow-md transition-all duration-300 group">
                        <div class="p-3 bg-primary/10 mb-4 group-hover:bg-primary/20 transition-colors duration-300">
                            <Icon icon="mdi:map-marker" class="w-8 h-8 text-primary" />
                        </div>
                        <h4 class="font-bold text-lg mb-2 text-gray-800">ADDRESS</h4>
                        <p class="text-sm text-gray-600">220E Front St. Burlington, NC 27215</p>
                    </div>
                    <div
                        class="bg-white p-6 flex flex-col items-center text-center shadow-sm border border-gray-100 hover:shadow-md transition-all duration-300 group">
                        <div class="p-3 bg-primary/10 mb-4 group-hover:bg-primary/20 transition-colors duration-300">
                            <Icon icon="mdi:phone" class="w-8 h-8 text-primary" />
                        </div>
                        <h4 class="font-bold text-lg mb-2 text-gray-800">PHONE</h4>
                        <p class="text-sm text-gray-600">+1 (007) 123-4567</p>
                        <p class="text-sm text-gray-600 mt-1">+1 (007) 987-6543</p>
                    </div>
                    <div
                        class="bg-white p-6 flex flex-col items-center text-center shadow-sm border border-gray-100 hover:shadow-md transition-all duration-300 group">
                        <div class="p-3 bg-primary/10 mb-4 group-hover:bg-primary/20 transition-colors duration-300">
                            <Icon icon="mdi:email-outline" class="w-8 h-8 text-primary" />
                        </div>
                        <h4 class="font-bold text-lg mb-2 text-gray-800">EMAIL</h4>
                        <p class="text-sm text-gray-600">info@carcorporations.com</p>
                        <p class="text-sm text-gray-600 mt-1">support@carcorporations.com</p>
                    </div>
                    <div
                        class="bg-white p-6 flex flex-col items-center text-center shadow-sm border border-gray-100 hover:shadow-md transition-all duration-300 group">
                        <div class="p-3 bg-primary/10 mb-4 group-hover:bg-primary/20 transition-colors duration-300">
                            <Icon icon="mdi:clock-outline" class="w-8 h-8 text-primary" />
                        </div>
                        <h4 class="font-bold text-lg mb-2 text-gray-800">BUSINESS HOURS</h4>
                        <p class="text-sm text-gray-600">Mon-Fri: 9AM - 6PM</p>
                        <p class="text-sm text-gray-600 mt-1">Sat: 10AM - 4PM</p>
                    </div>
                </div>
            </div>
        </section>
        <section class="relative w-full py-12 bg-gradient-to-br from-slate-50 via-white to-slate-100">
            <div class="container mx-auto px-4">
                <h2 class="text-3xl md:text-4xl font-bold text-center text-gray-800 mb-10">
                    Frequently Asked Questions
                </h2>

                <div class="max-w-full mx-auto space-y-4">
                    <div v-for="(faq, index) in faqs" :key="index"
                        class="border rounded-2xl overflow-hidden shadow-sm bg-white">
                        <button
                            class="w-full flex justify-between items-center px-6 py-4 text-left text-gray-800 font-medium hover:bg-gray-50 transition"
                            @click="toggleFAQ(index)">
                            <span>{{ faq.question }}</span>
                            <Icon icon="mdi:chevron-down"
                                class="w-6 h-6 text-gray-600 transform transition-transform duration-300"
                                :class="{ 'rotate-180': faq.open }" />
                        </button>

                        <!-- Answer -->
                        <div v-show="faq.open" class="px-6 pb-4 text-gray-600 animate-fade-in">
                            {{ faq.answer }}
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </section>
</template>
<style scoped></style>