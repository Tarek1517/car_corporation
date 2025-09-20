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
    avatar:
      "/images/avater3.png",
  },
  {
    id: 2,
    rating: 5.0,
    text: "The import process was handled perfectly. My Toyota Allion arrived in Bangladesh without any customs issues thanks to their professional team.",
    name: "Fatima Ahmed",
    role: "Business Owner",
    avatar:
      "/images/avater2.png",
  },
  {
    id: 3,
    rating: 4.8,
    text: "I've imported 5 vehicles through Car Corporations BD. Their auction access and negotiation skills have saved me thousands on each purchase.",
    name: "Tariqul Islam",
    role: "Car Dealer",
    avatar:
      "/images/avater1.png",
  },
  {
    id: 4,
    rating: 4.9,
    text: "The after-sales support exceeded my expectations. They helped with registration and even recommended a trusted mechanic for maintenance.",
    name: "Nusrat Jahan",
    role: "HR Executive",
    avatar:
      "/images/avater3.png",
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
      <img src="/images/testimonial.jpg" alt="Testimonials Background" class="w-full h-full object-cover" />
      <div class="absolute inset-0 bg-black/50"></div>
      <div class="absolute inset-0 flex flex-col items-center justify-center text-center px-4 z-10">
        <h2 class="text-4xl md:text-5xl font-bold text-white drop-shadow-lg mb-4">
          Our Clients
          <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary drop-shadow">
            Speak For Us
          </span>
        </h2>
        <p class="text-lg md:text-xl text-gray-200 max-w-2xl">
          Real stories from our customers — trust built through premium auction,
          import, and after-sales services.
        </p>
      </div>
    </div>

    <section class="py-16 md:py-24 bg-gradient-to-b from-slate-50 to-white">
      <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
        <div class="mb-16 text-center">
          <div class="inline-flex items-center justify-center mb-4">
            <div class="h-0.5 w-8 bg-primary mr-3"></div>
            <span class="text-sm font-semibold tracking-wider text-primary uppercase">Client Testimonials</span>
            <div class="h-0.5 w-8 bg-primary ml-3"></div>
          </div>
          <h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-4">
            What Our Satisfied Clients Say
          </h2>
          <p class="text-lg text-gray-600 max-w-2xl mx-auto">
            Hear from customers who have experienced our premium vehicle auction
            and import services.
          </p>
        </div>

        <div class="mx-auto max-w-7xl">
          <Swiper :modules="[Pagination, Autoplay]" :slides-per-view="1" :space-between="30" :loop="true"
            :centered-slides="true" :autoplay="{ delay: 5000, disableOnInteraction: false }"
            :pagination="{ el: '.testimonial-pagination', clickable: true }" :breakpoints="{
              640: { slidesPerView: 1 },
              768: { slidesPerView: 2 },
              1024: { slidesPerView: 3 },
            }" class="pb-16">
            <SwiperSlide v-for="item in testimonials" :key="item.id">
              <div
                class="group bg-white border border-gray-200 rounded-2xl p-8 transition-all duration-500 hover:border-primary/30 hover:shadow-lg h-full flex flex-col">
                <!-- Rating -->
                <div class="flex items-center mb-6 gap-1 text-amber-500">
                  <Icon v-for="star in 5" :key="star"
                    :icon="star <= Math.round(item.rating) ? 'mdi:star' : 'mdi:star-outline'" class="w-6 h-6" />
                  <span class="text-xl font-semibold text-gray-800 ml-2">{{ item.rating }}</span>
                </div>

                <!-- Feedback -->
                <p class="text-gray-700 leading-relaxed mb-8 flex-grow group-hover:text-gray-900 text-lg">
                  "{{ item.text }}"
                </p>

                <!-- Client Info -->
                <div class="flex items-center gap-4 border-t border-gray-100 pt-6 mt-auto">
                  <img :src="item.avatar" :alt="`${item.name} avatar`"
                    class="rounded-full h-16 w-16 object-cover shadow-md" />
                  <div>
                    <h5 class="text-gray-900 font-bold text-lg">
                      {{ item.name }}
                    </h5>
                    <span class="text-sm text-gray-600">{{ item.role }}</span>
                  </div>
                </div>
              </div>
            </SwiperSlide>

            <!-- Custom pagination -->
            <div class="testimonial-pagination flex justify-center mt-10 space-x-2"></div>
          </Swiper>
        </div>
      </div>
    </section>

    <!-- FAQ Section -->
    <section class="py-16 bg-white border-t border-gray-100">
      <div class="max-w-4xl mx-auto px-4">
        <h3 class="text-2xl md:text-3xl font-bold text-gray-900 mb-8 text-center">
          Frequently Asked Questions
        </h3>
        <div class="space-y-4">
          <div v-for="(faq, index) in faqs" :key="index"
            class="border border-gray-200 rounded-xl p-5 cursor-pointer hover:border-primary transition"
            @click="toggleFAQ(index)">
            <div class="flex justify-between items-center">
              <h4 class="text-lg font-semibold text-gray-800">
                {{ faq.question }}
              </h4>
              <Icon :icon="faq.open ? 'mdi:chevron-up' : 'mdi:chevron-down'" class="w-6 h-6 text-primary" />

            </div>
            <transition name="fade">
              <p v-if="faq.open" class="mt-3 text-gray-600 leading-relaxed animate-fade-in">
                {{ faq.answer }}
              </p>
            </transition>
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
  background-color: #d1d5db;
  opacity: 0.7;
  border-radius: 6px;
  transition: all 0.3s ease;
}

.testimonial-pagination :deep(.swiper-pagination-bullet-active) {
  background: #8b0000;
  opacity: 1;
  width: 30px;
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
