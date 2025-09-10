<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Pagination, Autoplay } from "swiper/modules";
import "swiper/css";
import "swiper/css/pagination";
import { ref } from "vue";
import { Icon } from "@iconify/vue"; 
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
const form = ref({
  name: "",
  email: "",
  phone: "",
  carModel: "",
  yearOfManufacture: "",
  carInsurance: "",
  carImage: null,
});

// Handle form submit
const handleSubmit = () => {
  console.log("Form Submitted:", form.value);
  alert("Thank you! Your insurance quote request has been submitted.");
};

// Handle file upload
const handleFileUpload = (event) => {
  const file = event.target.files[0];
  if (file) {
    form.value.carImage = file;
  }
};
</script>

<template>
  <section class="w-full relative overflow-hidden py-2 md:py-6 bg-gradient-to-br from-slate-50 via-white to-slate-100">
    <!-- Background blobs -->
    <div
      class="absolute top-0 right-0 w-96 h-96 bg-primary/10 rounded-full -translate-y-1/3 translate-x-1/3 blur-3xl animate-pulse-slow">
    </div>
    <div
      class="absolute bottom-0 left-0 w-[32rem] h-[32rem] bg-secondary/10 rounded-full translate-y-1/3 -translate-x-1/3 blur-3xl animate-pulse-slow delay-1000">
    </div>
    <div class="absolute top-1/2 left-1/4 w-64 h-64 bg-primary/5 rounded-full blur-3xl animate-pulse-slow delay-500">
    </div>
    <div class="absolute inset-0 opacity-[0.03] bg-grid-pattern"></div>

    <div class="relative z-10">
      <!-- Hero Section -->
      <div class="pb-12 relative">
        <div
          class="absolute top-0 left-0 w-64 h-64 bg-primary/5 rounded-full blur-3xl -translate-x-1/2 -translate-y-1/2">
        </div>
        <div
          class="absolute bottom-0 right-0 w-80 h-80 bg-secondary/5 rounded-full blur-3xl translate-x-1/3 translate-y-1/3">
        </div>

        <div class="relative z-10 text-center mb-16">
          <div class="relative h-[500px] md:h-[600px] w-full">
            <img src="../../public/images/herovison.jpg" alt="Car Financing Background"
              class="w-full h-full object-cover" />
            <div class="absolute inset-0 flex flex-col items-center justify-center text-center px-4 z-10">
              <h2 class="text-4xl md:text-5xl font-bold text-gray-100 mb-4">
                Drive Your
                <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">
                  Dream Car
                </span>
                with Easy Financing
              </h2>
              <p class="text-xl text-gray-100 max-w-2xl">
                Affordable car loans and flexible payment plans designed to make owning your dream car simple and
                stress-free.
              </p>
            </div>
          </div>
        </div>
        <div class="mb-1 flex items-center justify-center">
          <div class="h-0.5 w-8 bg-primary mr-3"></div>
          <span class="text-2xl font-semibold tracking-wider text-primary uppercase">Financial Support</span>
          <div class="h-0.5 w-8 bg-primary ml-3"></div>
        </div>
        <p class="text-gray-600 text-lg text-center max-w-3xl mx-auto">
          Helping clients finance and own cars easily with low-interest loans and customized payment options.
        </p>
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
          <div class="relative">

            <div class="rounded-2xl overflow-hidden shadow-xl border-4 border-white">
              <img src="../../public/images/vison1.jpg" alt="Our Journey" class="w-full h-full object-cover" />
            </div>
            <div
              class="absolute -bottom-6 -right-6 w-40 h-40 bg-gradient-to-r from-primary to-secondary rounded-2xl shadow-lg -z-10">
            </div>
          </div>

          <div>
            <h3 class="text-2xl font-bold text-gray-900 mb-6">Building Trust in Car Financing Since 2010</h3>
            <p class="text-gray-600 mb-6">
              Car Finance BD started with a vision to simplify car ownership for everyone. Today, we provide
              transparent, reliable, and quick financing solutions for all types of vehicles.
            </p>

            <div class="space-y-4 mb-8">
              <div class="flex items-start">
                <div class="bg-primary/10 p-2 rounded-lg mr-4 flex-shrink-0">
                  <Icon name="mdi:target" class="w-6 h-6 text-primary" />
                </div>
                <div>
                  <h4 class="font-semibold text-gray-900 mb-1">Ownership</h4>
                  <p class="text-gray-600 text-sm">
                    Make car ownership accessible through flexible loans and expert financial guidance.
                  </p>
                </div>
              </div>

              <div class="flex items-start">
                <div class="bg-secondary/10 p-2 rounded-lg mr-4 flex-shrink-0">
                  <Icon name="mdi:eye-outline" class="w-6 h-6 text-secondary" />
                </div>
                <div>
                  <h4 class="font-semibold text-gray-900 mb-1">Financing Support</h4>
                  <p class="text-gray-600 text-sm">
                    To be the most trusted car financing partner in Bangladesh.
                  </p>
                </div>
              </div>
            </div>

            <div class="flex gap-4">
              <div class="bg-gray-50 rounded-lg px-4 py-3">
                <div class="text-2xl font-bold text-primary">120K+</div>
                <div class="text-sm text-gray-500">Loans Approved</div>
              </div>
              <div class="bg-gray-50 rounded-lg px-4 py-3">
                <div class="text-2xl font-bold text-primary">10K+</div>
                <div class="text-sm text-gray-500">Satisfied Clients</div>
              </div>
            </div>

            <button
              class="mt-8 px-6 py-3 bg-gradient-to-r from-primary to-secondary text-white rounded-lg font-medium shadow-lg hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1 flex items-center">
              <span>Learn More</span>
              <Icon name="mdi:arrow-right" class="ml-2 w-5 h-5" />
            </button>
          </div>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 md:gap-8">
          <!-- Card 1: Low Interest Rates -->
          <div
            class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-primary/20 hover:-translate-y-2 relative overflow-hidden">
            <div
              class="absolute top-0 right-0 w-28 h-28 bg-primary/5 rounded-bl-full transition-all duration-500 group-hover:bg-primary/10">
            </div>
            <div class="flex justify-start mb-5 relative z-10">
              <div
                class="p-3 bg-gradient-to-br from-primary/10 to-primary/5 rounded-xl transition-colors duration-500 group-hover:from-primary/15 group-hover:to-primary/10 shadow-sm">
                <Icon name="mdi:percent" class="w-7 h-7 text-primary" />
              </div>
            </div>
            <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
              Low Interest Rates
            </h3>
            <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
              Enjoy competitive rates designed to keep your monthly payments affordable.
            </p>
            <div class="flex items-center relative z-10">
              <div
                class="w-8 h-8 rounded-full bg-primary/5 flex items-center justify-center transition-colors duration-300 group-hover:bg-primary/10">
                <Icon name="mdi:arrow-right"
                  class="text-primary transition-all duration-500 transform group-hover:translate-x-1" />
              </div>
              <span
                class="text-primary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0">Check
                rates</span>
            </div>
          </div>

          <!-- Card 2: Flexible Payment Plans -->
          <div
            class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-secondary/20 hover:-translate-y-2 relative overflow-hidden">
            <div
              class="absolute top-0 right-0 w-28 h-28 bg-secondary/5 rounded-bl-full transition-all duration-500 group-hover:bg-secondary/10">
            </div>
            <div class="flex justify-start mb-5 relative z-10">
              <div
                class="p-3 bg-gradient-to-br from-secondary/10 to-secondary/5 rounded-xl transition-colors duration-500 group-hover:from-secondary/15 group-hover:to-secondary/10 shadow-sm">
                <Icon name="mdi:calendar-clock" class="w-7 h-7 text-secondary" />
              </div>
            </div>
            <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
              Flexible Payment Plans
            </h3>
            <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
              Choose from a variety of installment options that fit your budget and lifestyle.
            </p>
            <div class="flex items-center relative z-10">
              <div
                class="w-8 h-8 rounded-full bg-secondary/5 flex items-center justify-center transition-colors duration-300 group-hover:bg-secondary/10">
                <Icon name="mdi:arrow-right"
                  class="text-secondary transition-all duration-500 transform group-hover:translate-x-1" />
              </div>
              <span
                class="text-secondary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0">View
                plans</span>
            </div>
          </div>

          <!-- Card 3: Quick Approval -->
          <div
            class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-primary/20 hover:-translate-y-2 relative overflow-hidden">
            <div
              class="absolute top-0 right-0 w-28 h-28 bg-primary/5 rounded-bl-full transition-all duration-500 group-hover:bg-primary/10">
            </div>
            <div class="flex justify-start mb-5 relative z-10">
              <div
                class="p-3 bg-gradient-to-br from-primary/10 to-primary/5 rounded-xl transition-colors duration-500 group-hover:from-primary/15 group-hover:to-primary/10 shadow-sm">
                <Icon name="mdi:check-decagram" class="w-7 h-7 text-primary" />
              </div>
            </div>
            <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
              Quick Approval
            </h3>
            <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
              Get approved in as little as 24 hours with our hassle-free loan process.
            </p>
            <div class="flex items-center relative z-10">
              <div
                class="w-8 h-8 rounded-full bg-primary/5 flex items-center justify-center transition-colors duration-300 group-hover:bg-primary/10">
                <Icon name="mdi:arrow-right"
                  class="text-primary transition-all duration-500 transform group-hover:translate-x-1" />
              </div>
              <span
                class="text-primary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0">Apply
                now</span>
            </div>
          </div>

          <!-- Card 4: Trusted Support -->
          <div
            class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-secondary/20 hover:-translate-y-2 relative overflow-hidden">
            <div
              class="absolute top-0 right-0 w-28 h-28 bg-secondary/5 rounded-bl-full transition-all duration-500 group-hover:bg-secondary/10">
            </div>
            <div class="flex justify-start mb-5 relative z-10">
              <div
                class="p-3 bg-gradient-to-br from-secondary/10 to-secondary/5 rounded-xl transition-colors duration-500 group-hover:from-secondary/15 group-hover:to-secondary/10 shadow-sm">
                <Icon name="mdi:handshake" class="w-7 h-7 text-secondary" />
              </div>
            </div>
            <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
              Trusted Support
            </h3>
            <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
              Our financing experts guide you every step of the way, from application to ownership.
            </p>
            <div class="flex items-center relative z-10">
              <div
                class="w-8 h-8 rounded-full bg-secondary/5 flex items-center justify-center transition-colors duration-300 group-hover:bg-secondary/10">
                <Icon name="mdi:arrow-right"
                  class="text-secondary transition-all duration-500 transform group-hover:translate-x-1" />
              </div>
              <span
                class="text-secondary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0">Get
                help</span>
            </div>
          </div>
        </div>
        <!--Eligibility & Requirements list-->
        <div class="relative z-10 py-12">
          <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-12">
              <h2 class="text-3xl font-bold text-gray-900 mb-4">Eligibility & Requirements</h2>
              <p class="text-gray-600 max-w-2xl mx-auto">
                To qualify for our car financing options, applicants must meet the following criteria:
              </p>
            </div>
            <ul class="grid grid-cols-1 md:grid-cols-2 gap-8 max-w-4xl mx-auto">
              <li class="flex items-start">
                <div class="flex-shrink-0 mt-1">
                  <Icon name="mdi:check-circle" class="w-6 h-6 text-green-500" />
                </div>
                <div class="ml-4">
                  <h3 class="font-semibold text-lg text-gray-900">Age Requirement</h3>
                  <p class="text-gray-600 text-sm">Applicants must be at least 21 years old.</p>
                </div>
              </li>
              <li class="flex items-start">
                <div class="flex-shrink-0 mt-1">
                  <Icon name="mdi:check-circle" class="w-6 h-6 text-green-500" />
                </div>
                <div class="ml-4">
                  <h3 class="font-semibold text-lg text-gray-900">Income Proof</h3>
                  <p class="text-gray-600 text-sm">Provide proof of a stable income source.</p>
                </div>
              </li>
              <li class="flex items-start">
                <div class="flex-shrink-0 mt-1">
                  <Icon name="mdi:check-circle" class="w-6 h-6 text-green-500" />
                </div>
                <div class="ml-4">
                  <h3 class="font-semibold text-lg text-gray-900">Credit History</h3>
                  <p class="text-gray-600 text-sm">A good credit score is preferred but not mandatory.</p>
                </div>
              </li>
              <li class="flex items-start">
                <div class="flex-shrink-0 mt-1">
                  <Icon name="mdi:check-circle" class="w-6 h-6 text-green-500" />
                </div>
                <div class="ml-4">
                  <h3 class="font-semibold text-lg text-gray-900">Identification</h3>
                  <p class="text-gray-600 text-sm">Valid government-issued ID (e.g., passport, driver's license).</p>
                </div>
              </li>
            </ul>
          </div>
        </div>
        
      </div>
    </div>
    <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
        
      <div class="mb-16 text-center">
        <div class="inline-flex items-center justify-center mb-4">
          <div class="h-0.5 w-8 bg-primary mr-3"></div>
          <span class="text-sm font-semibold tracking-wider text-primary uppercase">CLIENT TESTIMONIALS</span>
          <div class="h-0.5 w-8 bg-primary ml-3"></div>
        </div>
        <h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-4">What Our Satisfied Clients Say</h2>
        <p class="text-lg text-gray-600 max-w-2xl mx-auto">
          Hear from customers who have experienced our premium vehicle auction and import services.
        </p>
      </div>
      
      <Swiper
        :modules="[Pagination, Autoplay]"
        :slides-per-view="1"
        :space-between="30"
        :loop="true"
        :centered-slides="true"
        :autoplay="{ delay: 5000, disableOnInteraction: false }"
        :pagination="{ clickable: true, el: '.testimonial-pagination' }"
        :breakpoints="{
          640: {
            slidesPerView: 1,
          },
          768: {
            slidesPerView: 2,
          },
          1024: {
            slidesPerView: 3,
          },
        }"
        class="pb-16"
      >
        <SwiperSlide v-for="item in testimonials" :key="item.id">
          <div
            class="group bg-white border border-gray-200 rounded-2xl p-6 transition-all duration-500 hover:border-primary/30 hover:shadow-lg h-full flex flex-col"
          >
            <div class="flex items-center mb-6 gap-1 text-amber-500">
              <Icon
                v-for="star in 5"
                :key="star"
                name="mdi:star"
                class="w-5 h-5"
              />
              <span class="text-base font-semibold text-gray-700 ml-2">{{ item.rating }}</span>
            </div>
            <p class="text-gray-600 leading-relaxed mb-8 flex-grow group-hover:text-gray-800">
              "{{ item.text }}"
            </p>
            <div class="flex items-center gap-4 border-t border-gray-100 pt-6 mt-auto">
              <img :src="item.avatar" alt="avatar" class="rounded-full h-12 w-12 object-cover shadow-sm" />
              <div>
                <h5 class="text-gray-900 font-semibold">{{ item.name }}</h5>
                <span class="text-sm text-gray-500">{{ item.role }}</span>
              </div>
            </div>
          </div>
        </SwiperSlide>
        
        <!-- Custom pagination container -->
        <div class="testimonial-pagination flex justify-center mt-10 space-x-2"></div>
      </Swiper>
      
    </div>
        <section class="relative w-full py-12 bg-gradient-to-br from-slate-50 via-white to-slate-100">
    <div class="container mx-auto px-4">
      <h2 class="text-3xl md:text-4xl font-bold text-center text-gray-800 mb-10">
        Frequently Asked Questions
      </h2>

      <div class="max-w-full mx-auto space-y-4">
        <div
          v-for="(faq, index) in faqs"
          :key="index"
          class="border rounded-2xl overflow-hidden shadow-sm bg-white"
        >
          <!-- Question -->
          <button
            class="w-full flex justify-between items-center px-6 py-4 text-left text-gray-800 font-medium hover:bg-gray-50 transition"
            @click="toggleFAQ(index)"
          >
            <span>{{ faq.question }}</span>
            <Icon
              icon="mdi:chevron-down"
              class="w-6 h-6 text-gray-600 transform transition-transform duration-300"
              :class="{ 'rotate-180': faq.open }"
            />
          </button>

          <!-- Answer -->
          <div
            v-show="faq.open"
            class="px-6 pb-4 text-gray-600 animate-fade-in"
          >
            {{ faq.answer }}
          </div>
        </div>
      </div>
    </div>
  </section>
            <!-- Application Form -->
<div class="bg-white rounded-2xl shadow-xl p-8 md:p-12 my-12 max-w-7xl mx-auto">
    <form @submit.prevent="handleSubmit" class="grid grid-cols-1 md:grid-cols-2 gap-6 max-w-3xl justify-center mx-auto">
        <h2 class="col-span-1 md:col-span-2 text-2xl font-bold text-gray-800 mb-4 text-center">Applicant Information</h2>
        
        <div class="col-span-1">
            <label class="block text-sm font-medium text-gray-700 mb-1">Full Name</label>
            <div class="relative">
                <span class="absolute left-3 top-3 text-gray-900">
                    <Icon name="mdi:account" class="w-8 h-8 text-primary" />
                </span>
                <input
                    v-model="form.fullName"
                    type="text"
                    placeholder="Enter your full name"
                    class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-900"
                    required
                />
            </div>
        </div>

        <div class="col-span-1">
            <label class="block text-sm font-medium text-gray-700 mb-1">Email Address</label>
            <div class="relative">
                <span class="absolute left-3 top-3 text-gray-400">
                    <Icon name="mdi:email" class="w-8 h-8 text-primary" />
                </span>
                <input
                    v-model="form.email"
                    type="email"
                    placeholder="Enter your email address"
                    class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-900"
                    required
                />
            </div>
        </div>

        <div class="col-span-1">
            <label class="block text-sm font-medium text-gray-700 mb-1">Phone Number</label>
            <div class="relative">
                <span class="absolute left-3 top-3 text-gray-400">
                    <Icon name="mdi:phone" class="w-8 h-8 text-primary" />
                </span>
                <input
                    v-model="form.phone"
                    type="tel"
                    placeholder="Enter your phone number"
                    class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-900"
                    required
                />
            </div>
        </div>

        <div class="col-span-1">
            <label class="block text-sm font-medium text-gray-700 mb-1">Annual Income</label>
            <div class="relative">
                <span class="absolute left-3 top-3 text-gray-400">
                    <Icon name="mdi:currency-usd" class="w-8 h-8 text-primary" />
                </span>
                <input
                    v-model="form.annualIncome"
                    type="number"
                    placeholder="Enter your annual income"
                    class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-900"
                    min="0"
                    required
                />
            </div>
        </div>

        <h2 class="col-span-1 md:col-span-2 text-2xl font-bold text-gray-800 mt-6 mb-4">Vehicle Information</h2>

        <div class="col-span-1">
            <label class="block text-sm font-medium text-gray-700 mb-1">Make</label>
            <div class="relative">
                <span class="absolute left-3 top-3 text-gray-400">
                    <Icon name="mdi:car" class="w-8 h-8 text-primary" />
                </span>
                <input
                    v-model="form.carMake"
                    type="text"
                    placeholder="e.g., Toyota, Honda"
                    class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-900"
                    required
                />
            </div>
        </div>

        <div class="col-span-1">
            <label class="block text-sm font-medium text-gray-700 mb-1">Model</label>
            <div class="relative">
                <span class="absolute left-3 top-3 text-gray-400">
                    <Icon name="mdi:car" class="w-8 h-8 text-primary" />
                </span>
                <input
                    v-model="form.carModel"
                    type="text"
                    placeholder="e.g., Camry, Civic"
                    class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-900"
                    required
                />
            </div>
        </div>

        <div class="col-span-1">
            <label class="block text-sm font-medium text-gray-700 mb-1">Year</label>
            <div class="relative">
                <span class="absolute left-3 top-3 text-gray-400">
                    <Icon name="mdi:calendar" class="w-8 h-8 text-primary" />
                </span>
                <input
                    v-model="form.carYear"
                    type="number"
                    placeholder="e.g., 2023"
                    class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-900"
                    min="1980"
                    :max="new Date().getFullYear() + 1"
                    required
                />
            </div>
        </div>

        <div class="col-span-1">
            <label class="block text-sm font-medium text-gray-700 mb-1">Vehicle Price ($)</label>
            <div class="relative">
                <span class="absolute left-3 top-3 text-gray-400">
                    <Icon name="mdi:tag" class="w-8 h-8 text-primary" />
                </span>
                <input
                    v-model="form.vehiclePrice"
                    type="number"
                    placeholder="Enter the vehicle price"
                    class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-900"
                    min="0"
                    required
                />
            </div>
        </div>

        <h2 class="col-span-1 md:col-span-2 text-2xl font-bold text-gray-800 mt-6 mb-4">Loan Details</h2>
        
        <div class="col-span-1">
            <label class="block text-sm font-medium text-gray-700 mb-1">Desired Loan Amount ($)</label>
            <div class="relative">
                <span class="absolute left-3 top-3 text-gray-400">
                    <Icon name="mdi:finance" class="w-8 h-8 text-primary" />
                </span>
                <input
                    v-model="form.loanAmount"
                    type="number"
                    placeholder="Enter desired loan amount"
                    class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-900"
                    min="0"
                    required
                />
            </div>
        </div>

        <div class="col-span-1">
            <label class="block text-sm font-medium text-gray-700 mb-1">Down Payment ($)</label>
            <div class="relative">
                <span class="absolute left-3 top-3 text-gray-400">
                    <Icon name="mdi:cash" class="w-8 h-8 text-primary" />
                </span>
                <input
                    v-model="form.downPayment"
                    type="number"
                    placeholder="Enter your down payment"
                    class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-900"
                    min="0"
                    required
                />
            </div>
        </div>

        <div class="col-span-1">
            <label class="block text-sm font-medium text-gray-700 mb-1">Loan Term (in months)</label>
            <div class="relative">
                <span class="absolute left-3 top-3 text-gray-400">
                    <Icon name="mdi:clock" class="w-8 h-8 text-primary" />
                </span>
                <input
                    v-model="form.loanTerm"
                    type="number"
                    placeholder="e.g., 60, 72"
                    class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-900"
                    min="12"
                    max="84"
                    required
                />
            </div>
        </div>

        <div class="col-span-1 md:col-span-2">
            <label class="block text-sm font-medium text-gray-700 mb-1">Additional Comments</label>
            <div class="relative">
                <span class="absolute left-3 top-3 text-gray-400">
                    <Icon name="mdi:comment" class="w-8 h-8 text-primary" />
                </span>
                <textarea
                    v-model="form.comments"
                    rows="4"
                    placeholder="Any additional information you'd like to share"
                    class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-900"
                ></textarea>
            </div>
        </div>

        <div class="col-span-1 md:col-span-2 flex justify-center">
            <button
                type="submit"
                class="px-8 py-3 bg-primary text-white font-semibold rounded-xl shadow-md hover:bg-primary/90 transition"
            >
                Submit Application
            </button>
        </div>
    </form>
</div>
  </section>
</template>
<style>
@keyframes pulse-slow {

  0%,
  100% {
    opacity: 0.4;
  }

  50% {
    opacity: 0.7;
  }
}

.animate-pulse-slow {
  animation: pulse-slow 8s cubic-bezier(0.4, 0, 0.6, 1) infinite;
}

.bg-grid-pattern {
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 32 32' width='32' height='32' fill='none' stroke='rgb(15 23 42 / 0.05)'%3e%3cpath d='M0 .5H31.5V32'/%3e%3c/svg%3e");
}

.custom-bullet {
  display: inline-block;
  width: 10px;
  height: 10px;
  background-color: rgba(255, 255, 255, 0.6);
  border-radius: 50%;
  margin: 0 4px;
  cursor: pointer;
  transition: all 0.3s ease;
}

.custom-bullet-active {
  background-color: #fff;
  width: 24px;
  border-radius: 8px;
}

/* Smooth transitions for all elements */
* {
  transition-property: color, background-color, border-color, transform, box-shadow;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 300ms;
}
</style>
