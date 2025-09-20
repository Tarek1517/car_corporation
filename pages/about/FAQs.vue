<script setup>
import { ref } from "vue";
import { Icon } from "@iconify/vue";

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
  {
    question: "How can I participate in Japanese car auctions?",
    answer:
      "You can register with us, submit a refundable deposit, and our team will help you bid on your preferred vehicles directly from Japanese auctions.",
    open: false,
  },
  {
    question: "Do you help with import duty and registration?",
    answer:
      "Yes, we guide you through the full import process including duty calculation, customs clearance, and BRTA registration in Bangladesh.",
    open: false,
  },
  {
    question: "What documents are required to buy a car?",
    answer:
      "You’ll need a valid NID/Passport, proof of address, and in case of financing, additional documents as required by the bank.",
    open: false,
  },
  {
    question: "Do you provide after-sales service and parts?",
    answer:
      "Yes, our service centers offer regular maintenance, repairs, and genuine spare parts for Japanese and other vehicles.",
    open: false,
  },
]);
  
const toggleFAQ = (index) => {
  faqs.value[index].open = !faqs.value[index].open;
};
</script>


<template>
  <section
    class="w-full relative overflow-hidden bg-gradient-to-br from-slate-50 via-white to-slate-100"
  >
    <div
      class="absolute top-0 right-0 w-96 h-96 bg-primary/10 rounded-full -translate-y-1/3 translate-x-1/3 blur-3xl animate-pulse-slow"
    ></div>
    <div
      class="absolute bottom-0 left-0 w-[32rem] h-[32rem] bg-secondary/10 rounded-full translate-y-1/3 -translate-x-1/3 blur-3xl animate-pulse-slow delay-1000"
    ></div>
    <div class="absolute inset-0 opacity-[0.04] bg-grid-pattern"></div>

    <div class="relative z-10">
      <div class="relative h-[400px] md:h-[500px] w-full overflow-hidden shadow-lg">
        <img
          src="/images/faqs.jpg"
          alt="FAQ Background"
          class="w-full h-full object-cover"
        />
        <div class="absolute inset-0 bg-black/60"></div>
        <div
          class="absolute inset-0 flex flex-col items-center justify-center text-center z-10 px-4"
        >
          <h2
            class="text-4xl md:text-5xl font-bold text-white drop-shadow-lg mb-4"
          >
            Frequently Asked
            <span
              class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary"
            >Questions</span
            >
          </h2>
          <p class="text-lg md:text-xl text-gray-200 max-w-2xl">
            Find quick answers to the most common questions our customers ask
            about Car Corporation’s services, financing, and support.
          </p>
        </div>
      </div>
    </div>
    <section class="py-16 bg-white border-t border-gray-100">
      <div class="max-w-4xl mx-auto px-4">
        <h3 class="text-2xl md:text-3xl font-bold text-gray-900 mb-8 text-center">
          Frequently Asked Questions
        </h3>
        <div class="space-y-4">
          <div
            v-for="(faq, index) in faqs"
            :key="index"
            class="border border-gray-200 rounded-xl p-5 cursor-pointer hover:border-primary transition"
            @click="toggleFAQ(index)"
          >
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
/*
  The transition class styles for a smooth fade effect.
  These classes are automatically applied by Vue's <transition> component.
*/
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

/*
  A simple keyframe animation for the fade-in effect.
  This is used in the `animate-fade-in` class.
*/
@keyframes fade-in {
  from {
    opacity: 0;
    transform: translateY(-10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in {
  animation: fade-in 0.5s ease-out forwards;
}

/* Custom styles for background patterns and blobs.
  These are necessary for the decorative elements in the hero section.
*/
@keyframes pulse-slow {
  0%, 100% {
    transform: scale(1) rotate(0deg);
  }
  50% {
    transform: scale(1.05) rotate(5deg);
  }
}

.animate-pulse-slow {
  animation: pulse-slow 6s infinite ease-in-out;
}

.bg-grid-pattern {
  background-size: 20px 20px;
  background-image: radial-gradient(circle, #000000 1px, rgba(0, 0, 0, 0) 1px);
}

</style>