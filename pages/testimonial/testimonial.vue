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
</script>
<template>
  <section class="relative w-full overflow-hidden bg-gradient-to-br from-slate-50 via-white to-slate-100">
    <div class="relative h-[500px] md:h-[600px] w-full">
      <img src="../../public/images/testimonial.jpg" alt="Testimonials Background"
        class="w-full h-full object-cover" />
      <div class="absolute inset-0 bg-black/50"></div>
      <div class="absolute inset-0 flex flex-col items-center justify-center text-center px-4 z-10">
        <h2 class="text-4xl md:text-5xl font-bold text-white drop-shadow-lg mb-4">
          Our
          <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary drop-shadow">
            Testimonials
          </span>
        </h2>
        <p class="text-lg md:text-xl text-gray-200 max-w-2xl">
          Discover what our customers have to say — real experiences,
          genuine feedback, and stories that inspire trust in Car Corporation.
        </p>
      </div>
    </div>
    <HomeBlogSection />
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
  </section>
</template>
<style scoped>
.testimonial-pagination :deep(.swiper-pagination-bullet) {
  width: 12px;
  height: 12px;
  background-color: #D1D5DB;
  opacity: 0.7;
  border-radius: 6px;
  transition: all 0.3s ease;
}

.testimonial-pagination :deep(.swiper-pagination-bullet-active) {
  background: #8b0000;
  opacity: 1;
  width: 30px;
}

.group {
  transition: all 0.3s ease;
}
.animate-fade-in {
  animation: fadeIn 0.3s ease-in-out;
}
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(-4px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>