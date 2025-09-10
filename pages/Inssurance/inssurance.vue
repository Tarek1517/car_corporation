<script setup>
import { ref } from "vue";
import { Swiper, SwiperSlide } from "swiper/vue";
import { Pagination, Autoplay } from "swiper/modules";
import "swiper/css";
import "swiper/css/pagination";
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
  <section
    class="w-full relative overflow-hidden py-2 md:py-6 bg-gradient-to-br from-slate-50 via-white to-slate-100"
  >
    <!-- Background blobs -->
    <div
      class="absolute top-0 right-0 w-96 h-96 bg-primary/10 rounded-full -translate-y-1/3 translate-x-1/3 blur-3xl animate-pulse-slow"
    ></div>
    <div
      class="absolute bottom-0 left-0 w-[32rem] h-[32rem] bg-secondary/10 rounded-full translate-y-1/3 -translate-x-1/3 blur-3xl animate-pulse-slow delay-1000"
    ></div>
    <div
      class="absolute top-1/2 left-1/4 w-64 h-64 bg-primary/5 rounded-full blur-3xl animate-pulse-slow delay-500"
    ></div>
    <div class="absolute inset-0 opacity-[0.03] bg-grid-pattern"></div>

<div class="relative z-10">
      <!-- Hero Section -->
<div class="text-center ">
  <section class="relative bg-gradient-to-br from-slate-50 via-white to-slate-100">
    <div class="relative h-[500px] md:h-[600px] w-full">
      <!-- Background Image -->
      <img
        src="../../public/images/inssureance.jpg"
        alt="Car Insurance Background"
        class="w-full h-full object-cover"
      />
      <!-- Dark Overlay -->
      <div class="absolute inset-0 bg-black/40"></div>
      <!-- Text Content -->
      <div class="absolute inset-0 flex flex-col items-center justify-center text-center px-4 z-10">
        <h2 class="text-4xl md:text-5xl font-bold text-white mb-4">
          Get Your
          <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">
            Car Insured Today
          </span>
        </h2>
        <p class="text-xl text-white max-w-2xl">
          Fast, Affordable, and Reliable Car Insurance Plans
        </p>
      </div>
    </div>
  </section>
</div>


      <!-- Quote Form Section -->
      <div class="py-16 bg-gradient-to-br from-slate-50 via-white to-slate-100">
        <div class="max-w-5xl mx-auto px-6">
          <!-- Title -->
          <div class="text-center mb-12">
            <h2 class="text-3xl md:text-4xl font-bold text-gray-800">
              Insurance <span class="text-primary">Quote Form</span>
            </h2>
            <p class="mt-2 text-gray-600">
              Fill up the Form to get the insurance quote
            </p>
          </div>

          <!-- Contact Form -->
          <div class="bg-white rounded-2xl shadow-xl p-8 md:p-12">
            <form @submit.prevent="handleSubmit" class="grid grid-cols-1 md:grid-cols-2 gap-6">
              <!-- Name -->
              <div class="col-span-1">
                <label class="block text-sm font-medium text-gray-700 mb-1">Name</label>
                <div class="relative">
                  <span class="absolute left-3 top-3 text-gray-900">
                    <Icon name="mdi:account" class="w-8 h-8 text-primary" />
                  </span>
                  <input
                    v-model="form.name"
                    type="text"
                    placeholder="Enter your name"
                    class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-900"
                    required
                  />
                </div>
              </div>

              <!-- Email -->
              <div class="col-span-1">
                <label class="block text-sm font-medium text-gray-700 mb-1">Email</label>
                <div class="relative">
                  <span class="absolute left-3 top-3 text-gray-400">
                    <Icon name="mdi:email" class="w-8 h-8 text-primary" />
                  </span>
                  <input
                    v-model="form.email"
                    type="email"
                    placeholder="Enter your email"
                    class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-900"
                    required
                  />
                </div>
              </div>

              <!-- Phone -->
              <div class="col-span-1">
                <label class="block text-sm font-medium text-gray-700 mb-1">Phone</label>
                <div class="relative">
                  <span class="absolute left-3 top-3 text-gray-400">
                    <Icon name="mdi:phone" class="w-8 h-8 text-primary" />
                  </span>
                  <input
                    v-model="form.phone"
                    type="text"
                    placeholder="Enter your phone"
                    class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-900"
                  />
                </div>
              </div>

              <!-- Car Model -->
              <div class="col-span-1 md:col-span-2">
                <label class="block text-sm font-medium text-gray-700 mb-1">Car Model</label>
                <div class="relative">
                  <span class="absolute left-3 top-3 text-gray-400">
                    <Icon name="mdi:car" class="w-8 h-8 text-primary" />
                  </span>
                  <select
                    v-model="form.carModel"
                    class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-900"
                  >
                    <option value="" disabled>Select your car model</option>
                    <option value="sedan">Sedan</option>
                    <option value="suv">SUV</option>
                    <option value="truck">Truck</option>
                    <option value="coupe">Coupe</option>
                    <option value="convertible">Convertible</option>
                    <option value="hatchback">Hatchback</option>
                    <option value="minivan">Minivan</option>
                    <option value="wagon">Wagon</option>
                  </select>
                </div>
              </div>

              <!-- Year of Manufacture -->
              <div class="col-span-1 md:col-span-2">
                <label class="block text-sm font-medium text-gray-700 mb-1">Year of Manufacture</label>
                <div class="relative">
                  <span class="absolute left-3 top-3 text-gray-400">
                    <Icon name="mdi:calendar" class="w-8 h-8 text-primary" />
                  </span>
                  <input
                    v-model="form.yearOfManufacture"
                    type="number"
                    placeholder="Enter year"
                    class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-900"
                    min="1980"
                    max="2024"
                  />
                </div>
              </div>

              <!-- Insurance Type -->
              <div class="col-span-1 md:col-span-2">
                <label class="block text-sm font-medium text-gray-700 mb-1">Insurance Type</label>
                <div class="relative">
                  <span class="absolute left-3 top-3 text-gray-400">
                    <Icon name="mdi:paper" class="w-8 h-8 text-primary" />
                  </span>
                  <select
                    v-model="form.carInsurance"
                    class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-900"
                  >
                    <option value="" disabled>Select your car Insurance</option>
                    <option value="third-party">Third-Party</option>
                    <option value="personal-accident">Personal Accident</option>
                  </select>
                </div>
              </div>

              <!-- Image Upload -->
              <div class="col-span-1 md:col-span-2">
                <label class="block text-sm font-medium text-gray-700 mb-1">Upload Car Image</label>
                <div class="relative">
                  <span class="absolute left-3 top-3 text-gray-400">
                    <Icon name="mdi:image" class="w-8 h-8 text-primary" />
                  </span>
                  <input
                    @change="handleFileUpload"
                    type="file"
                    accept="image/*"
                    class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-900"
                  />
                </div>
              </div>

              <!-- Submit Button -->
              <div class="col-span-1 md:col-span-2 flex justify-center">
                <button
                  type="submit"
                  class="px-8 py-3 bg-primary text-white font-semibold rounded-xl shadow-md hover:bg-primary/90 transition"
                >
                  Submit
                </button>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
    <div class="max-w-7xl justify-center items-center mx-auto px-4 sm:px-6 lg:px-8 mb-8">
        <!-- Insurance Benefits / Features -->
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 md:gap-8">

  <!-- Card 1: Comprehensive Coverage -->
  <div
    class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-primary/20 hover:-translate-y-2 relative overflow-hidden">
    <div
      class="absolute top-0 right-0 w-28 h-28 bg-primary/5 rounded-bl-full transition-all duration-500 group-hover:bg-primary/10">
    </div>
    <div class="flex justify-start mb-5 relative z-10">
      <div
        class="p-3 bg-gradient-to-br from-primary/10 to-primary/5 rounded-xl transition-colors duration-500 group-hover:from-primary/15 group-hover:to-primary/10 shadow-sm">
        <Icon name="mdi:shield-car" class="w-7 h-7 text-primary" />
      </div>
    </div>
    <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
      Comprehensive Coverage
    </h3>
    <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
      Covers damages to your car and third-party liabilities, protecting you against accidents, theft, and natural disasters.
    </p>
    <div class="flex items-center relative z-10">
      <div
        class="w-8 h-8 rounded-full bg-primary/5 flex items-center justify-center transition-colors duration-300 group-hover:bg-primary/10">
        <Icon name="mdi:arrow-right" class="text-primary transition-all duration-500 transform group-hover:translate-x-1" />
      </div>
      <span class="text-primary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0">Learn More</span>
    </div>
  </div>

  <!-- Card 2: Affordable Premiums -->
  <div
    class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-secondary/20 hover:-translate-y-2 relative overflow-hidden">
    <div
      class="absolute top-0 right-0 w-28 h-28 bg-secondary/5 rounded-bl-full transition-all duration-500 group-hover:bg-secondary/10">
    </div>
    <div class="flex justify-start mb-5 relative z-10">
      <div
        class="p-3 bg-gradient-to-br from-secondary/10 to-secondary/5 rounded-xl transition-colors duration-500 group-hover:from-secondary/15 group-hover:to-secondary/10 shadow-sm">
        <Icon name="mdi:currency-bdt" class="w-7 h-7 text-secondary" />
      </div>
    </div>
    <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
      Affordable Premiums
    </h3>
    <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
      Flexible plans designed to fit your budget without compromising on coverage or quality of service.
    </p>
    <div class="flex items-center relative z-10">
      <div
        class="w-8 h-8 rounded-full bg-secondary/5 flex items-center justify-center transition-colors duration-300 group-hover:bg-secondary/10">
        <Icon name="mdi:arrow-right" class="text-secondary transition-all duration-500 transform group-hover:translate-x-1" />
      </div>
      <span class="text-secondary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0">View Plans</span>
    </div>
  </div>

  <!-- Card 3: 24/7 Assistance -->
  <div
    class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-primary/20 hover:-translate-y-2 relative overflow-hidden">
    <div
      class="absolute top-0 right-0 w-28 h-28 bg-primary/5 rounded-bl-full transition-all duration-500 group-hover:bg-primary/10">
    </div>
    <div class="flex justify-start mb-5 relative z-10">
      <div
        class="p-3 bg-gradient-to-br from-primary/10 to-primary/5 rounded-xl transition-colors duration-500 group-hover:from-primary/15 group-hover:to-primary/10 shadow-sm">
        <Icon name="mdi:headset" class="w-7 h-7 text-primary" />
      </div>
    </div>
    <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
      24/7 Assistance
    </h3>
    <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
      Round-the-clock support for claims, roadside assistance, and customer service to give you peace of mind.
    </p>
    <div class="flex items-center relative z-10">
      <div
        class="w-8 h-8 rounded-full bg-primary/5 flex items-center justify-center transition-colors duration-300 group-hover:bg-primary/10">
        <Icon name="mdi:arrow-right" class="text-primary transition-all duration-500 transform group-hover:translate-x-1" />
      </div>
      <span class="text-primary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0">Contact Support</span>
    </div>
  </div>

  <!-- Card 4: Quick Claims -->
  <div
    class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-secondary/20 hover:-translate-y-2 relative overflow-hidden">
    <div
      class="absolute top-0 right-0 w-28 h-28 bg-secondary/5 rounded-bl-full transition-all duration-500 group-hover:bg-secondary/10">
    </div>
    <div class="flex justify-start mb-5 relative z-10">
      <div
        class="p-3 bg-gradient-to-br from-secondary/10 to-secondary/5 rounded-xl transition-colors duration-500 group-hover:from-secondary/15 group-hover:to-secondary/10 shadow-sm">
        <Icon name="mdi:file-document-edit-outline" class="w-7 h-7 text-secondary" />
      </div>
    </div>
    <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
      Quick Claims
    </h3>
    <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
      Hassle-free claims process with fast approval times and minimal paperwork.
    </p>
    <div class="flex items-center relative z-10">
      <div
        class="w-8 h-8 rounded-full bg-secondary/5 flex items-center justify-center transition-colors duration-300 group-hover:bg-secondary/10">
        <Icon name="mdi:arrow-right" class="text-secondary transition-all duration-500 transform group-hover:translate-x-1" />
      </div>
      <span class="text-secondary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0">File a Claim</span>
    </div>
  </div>

</div>
          <section class="py-16 md:py-24 bg-gradient-to-b from-slate-50 to-white">
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
  </section>
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
    </div>
  </section>
</template>
