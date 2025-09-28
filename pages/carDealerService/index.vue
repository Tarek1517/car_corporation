<script setup>
import { ref, onMounted } from 'vue';
import { Icon } from '@iconify/vue';
const isLoaded = ref(false);
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

onMounted(() => {
  setTimeout(() => {
    isLoaded.value = true;
  }, 100);
});
</script>

<template>
  <section
    class="w-full relative overflow-hidden py-2 md:py-6 bg-gradient-to-br from-slate-900 via-slate-800 to-slate-900">
    <div
      class="absolute top-0 right-0 w-96 h-96 bg-blue-500/10 rounded-full -translate-y-1/3 translate-x-1/3 blur-3xl animate-pulse-slow">
    </div>
    <div
      class="absolute bottom-0 left-0 w-[32rem] h-[32rem] bg-indigo-600/10 rounded-full translate-y-1/3 -translate-x-1/3 blur-3xl animate-pulse-slow delay-1000">
    </div>
    <div class="absolute top-1/2 left-1/4 w-64 h-64 bg-cyan-500/5 rounded-full blur-3xl animate-pulse-slow delay-500">
    </div>
    <div class="absolute inset-0 opacity-[0.05] bg-grid-pattern"></div>
    <div class="absolute inset-0 bg-gradient-to-b from-transparent via-black/20 to-black/40"></div>
    <div class="absolute top-0 left-0 w-full h-full bg-pir"></div>
    <div class="relative z-10">
      <section class="relative">
        <div class="relative h-[400px] md:h-[500px] w-full overflow-hidden">
          <img src="../../public/images/serviceHero.jpg" alt="Luxury car showroom with premium vehicles"
            class="w-full h-full object-cover scale-105 transform transition-transform duration-10000 hover:scale-110" />
          <div class="absolute inset-0 bg-gradient-to-r from-black/70 via-black/50 to-transparent"></div>
          <div class="absolute inset-0 flex flex-col items-end justify-center px-8 md:px-16 text-right z-10">
            <div
              class="mb-4 px-3 py-1 bg-blue-500/20 backdrop-blur-sm rounded-full border border-blue-400/30 text-blue-300 text-sm font-medium animate-fade-in-down">
              ESTABLISHED 2010
            </div>
            <h2 class="text-5xl md:text-7xl font-bold text-white mb-4 drop-shadow-lg transition-all duration-1000"
              :class="isLoaded ? 'translate-y-0 opacity-100' : 'translate-y-10 opacity-0'">
              Premium
              <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">
                Automotive
              </span>
              <br>
              <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">
                Dealership
              </span>
            </h2>
            <p class="text-xl md:text-2xl text-white max-w-2xl drop-shadow-md mb-8 transition-all duration-1000 delay-300"
              :class="isLoaded ? 'translate-y-0 opacity-100' : 'translate-y-10 opacity-0'">
              Experience excellence with our curated selection of premium vehicles,
              transparent pricing, and white-glove service from experts who share your passion.
            </p>
            <div class="flex flex-col sm:flex-row gap-4 transition-all duration-1000 delay-500"
              :class="isLoaded ? 'translate-y-0 opacity-100' : 'translate-y-10 opacity-0'">
              <button
                class="px-8 py-3 bg-gradient-to-r from-primary to-secondary text-white rounded-xl font-semibold text-lg shadow-lg hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1 hover:scale-105 flex items-center justify-center gap-2 group">
                <span>Explore Inventory</span>
              </button>
              <button
                class="px-8 py-3 bg-transparent border-2 border-white/30 text-white rounded-xl font-semibold text-lg backdrop-blur-sm hover:bg-white/10 transition-all duration-300 flex items-center justify-center gap-2 group">
                <span>Speak with Expert</span>
              </button>
            </div>
          </div>
          <div class="absolute bottom-0 left-0 w-full h-24 bg-gradient-to-b from-transparent via-black/20 to-black/40">
          </div>
          <div class="absolute bottom-6 left-6 flex items-center gap-2 text-white/80 text-sm">
            <Icon icon="mdi:clock-time-four-outline" class="w-4 h-4" />
            <span>Open until 9AM</span>
          </div>
        </div>
      </section>
      <section class="bg-gradient-to-br from-slate-50 via-white to-slate-100 py-12 md:py-16">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center max-w-7xl mx-auto px-6 relative z-10">
          <div class="relative">
            <div class="rounded-2xl overflow-hidden shadow-xl border-4 border-white">
              <img src="../../public/images/OurReconditionVehicles.jpg" alt="Our Story"
                class="w-full h-full object-cover" />
            </div>
          </div>
          <div class="max-w-7xl mx-auto px-8 md:px-16">
            <div class="mb-4 flex items-center justify-center">
              <div class="h-0.5 w-8 bg-primary mr-3"></div>
              <span class="text-sm font-semibold tracking-wider text-primary uppercase">Detailed Services</span>
              <div class="h-0.5 w-8 bg-primary ml-3"></div>
            </div>
            <p class="text-gray-600 text-lg max-w-3xl mx-auto">
              From humble beginnings to becoming a trusted name in vehicle auctions and imports
            </p>
            <h3 class="text-2xl font-bold text-gray-900 mb-6">Building Trust in Vehicle Auctions Since 2010</h3>

            <p class="text-gray-600 mb-6">
              Car Corporations BD began with a simple vision: to provide Bangladeshi customers with direct access
              to global vehicle auctions, particularly the prestigious Japanese markets. What started as a small
              operation has grown into a premier service provider with thousands of successful imports.
            </p>

            <div class="space-y-4 mb-8">
              <div class="flex items-start">
                <div class="bg-primary/10 p-2 rounded-lg mr-4 flex-shrink-0">
                  <Icon icon="mdi:target" class="w-6 h-6 text-primary" />
                </div>
                <div>
                  <h4 class="font-semibold text-gray-900 mb-1">Test Drives</h4>
                  <p class="text-gray-600 text-sm">
                    Booking info, available models.
                  </p>
                </div>
              </div>

              <div class="flex items-start">
                <div class="bg-secondary/10 p-2 rounded-lg mr-4 flex-shrink-0">
                  <Icon icon="mdi:eye-outline" class="w-6 h-6 text-secondary" />
                </div>
                <div>
                  <h4 class="font-semibold text-gray-900 mb-1">Trade-In</h4>
                  <p class="text-gray-600 text-sm">
                    How customers can exchange old cars.
                  </p>
                </div>
              </div>
            </div>

            <div class="flex gap-4">
              <div class="bg-gray-50 rounded-lg px-4 py-3">
                <div class="text-2xl font-bold text-primary">12K+</div>
                <div class="text-sm text-gray-500">Customer Satisfaction</div>
              </div>
              <div class="bg-gray-50 rounded-lg px-4 py-3">
                <div class="text-2xl font-bold text-primary">10K+</div>
                <div class="text-sm text-gray-500">Trade In</div>
              </div>
            </div>

            <button
              class="mt-8 px-6 py-3 bg-gradient-to-r from-primary to-secondary text-white rounded-lg font-medium shadow-lg hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1 flex items-center">
              <span>Read Full Story</span>
              <Icon icon="mdi:arrow-right" class="ml-2 w-5 h-5" />
            </button>
          </div>
        </div>
      </section>
      <section class="bg-gradient-to-br from-slate-50 via-white to-slate-100 py-12 md:py-16">
        <div class="relative z-10 text-center mb-12">
          <h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-4">
            Benefits <span
              class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">Section</span>
          </h2>
          <p class="text-lg md:text-xl text-gray-600 max-w-3xl mx-auto">
            Discover our exclusive selection of premium vehicles, each meticulously inspected and ready to elevate your
            driving experience.
          </p>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 md:gap-8 max-w-7xl mx-auto px-6 relative z-10">
          <div
            class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-primary/20 hover:-translate-y-2 relative overflow-hidden">
            <div
              class="absolute top-0 right-0 w-28 h-28 bg-primary/5 rounded-bl-full transition-all duration-500 group-hover:bg-primary/10">
            </div>
            <div class="flex justify-start mb-5 relative z-10">
              <div
                class="p-3 bg-gradient-to-br from-primary/10 to-primary/5 rounded-xl transition-colors duration-500 group-hover:from-primary/15 group-hover:to-primary/10 shadow-sm">
                <Icon icon="mdi:certificate" class="w-7 h-7 text-primary" />
              </div>
            </div>
            <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
              Certified Dealership
            </h3>
            <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
              Officially licensed dealership ensuring authenticity, trust, and quality service for every vehicle.
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
                <Icon icon="mdi:account-group" class="w-7 h-7 text-secondary" />
              </div>
            </div>
            <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
              Experienced Staff
            </h3>
            <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
              A dedicated team of experts providing guidance, consultation, and seamless support throughout your
              journey.
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
              Transparent Pricing
            </h3>
            <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
              Clear, upfront pricing with no hidden costs, ensuring trust and confidence in every transaction.
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
                <Icon icon="mdi:shield-check" class="w-7 h-7 text-secondary" />
              </div>
            </div>
            <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
              Warranty & After-sales
            </h3>
            <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
              Full warranty coverage and dedicated after-sales service to keep your vehicle running smoothly.
            </p>
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
              <!-- Question -->
              <button
                class="w-full flex justify-between items-center px-6 py-4 text-left text-gray-800 font-medium hover:bg-gray-50 transition"
                @click="toggleFAQ(index)">
                <span>{{ faq.question }}</span>
                <Icon icon="mdi:chevron-down" class="w-6 h-6 text-gray-600 transform transition-transform duration-300"
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
      <section class="relative w-full py-12 bg-gradient-to-br from-slate-50 via-white to-slate-100">
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

            <!-- Address -->
            <div
              class="bg-white p-6 flex flex-col items-center text-center shadow-sm border border-gray-100 hover:shadow-md transition-all duration-300 group">
              <div class="p-3 bg-primary/10 mb-4 group-hover:bg-primary/20 transition-colors duration-300">
                <Icon icon="mdi:map-marker" class="w-8 h-8 text-primary" />
              </div>
              <h4 class="font-bold text-lg mb-2 text-gray-800">ADDRESS</h4>
              <p class="text-sm text-gray-600">220E Front St. Burlington, NC 27215</p>
            </div>

            <!-- Phone -->
            <div
              class="bg-white p-6 flex flex-col items-center text-center shadow-sm border border-gray-100 hover:shadow-md transition-all duration-300 group">
              <div class="p-3 bg-primary/10 mb-4 group-hover:bg-primary/20 transition-colors duration-300">
                <Icon icon="mdi:phone" class="w-8 h-8 text-primary" />
              </div>
              <h4 class="font-bold text-lg mb-2 text-gray-800">PHONE</h4>
              <p class="text-sm text-gray-600">+1 (007) 123-4567</p>
              <p class="text-sm text-gray-600 mt-1">+1 (007) 987-6543</p>
            </div>

            <!-- Email -->
            <div
              class="bg-white p-6 flex flex-col items-center text-center shadow-sm border border-gray-100 hover:shadow-md transition-all duration-300 group">
              <div class="p-3 bg-primary/10 mb-4 group-hover:bg-primary/20 transition-colors duration-300">
                <Icon icon="mdi:email-outline" class="w-8 h-8 text-primary" />
              </div>
              <h4 class="font-bold text-lg mb-2 text-gray-800">EMAIL</h4>
              <p class="text-sm text-gray-600">info@carcorporations.com</p>
              <p class="text-sm text-gray-600 mt-1">support@carcorporations.com</p>
            </div>

            <!-- Business Hours -->
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
        <iframe
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3237.7170532222874!2d-79.4371!3d36.0957!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x88531365c32e0a17%3A0x1234567890abcdef!2s220E%20Front%20St%2C%20Burlington%2C%20NC!5e0!3m2!1sen!2sus!4v1695678901234!5m2!1sen!2sus"
          width="100%" height="300" style="border:0;" allowfullscreen="" loading="lazy"
          referrerpolicy="no-referrer-when-downgrade">
        </iframe>
      </section>
      <div class="relative w-full py-12 bg-gradient-to-br from-slate-50 via-white to-slate-100">
        <p class="text-center text-gray-500 text-sm mb-6">Trusted by automotive enthusiasts and businesses nationwide
        </p>
        <div class="flex flex-wrap justify-center gap-8 md:gap-12 opacity-60">
          <div class="h-8 w-auto grayscale hover:grayscale-0 transition-all">
            <Icon icon="mdi:shield-check" class="w-full h-full text-primary" />
          </div>
          <div class="h-8 w-auto grayscale hover:grayscale-0 transition-all">
            <Icon icon="mdi:medal" class="w-full h-full text-primary" />
          </div>
          <div class="h-8 w-auto grayscale hover:grayscale-0 transition-all">
            <Icon icon="mdi:account-group" class="w-full h-full text-primary" />
          </div>
          <div class="h-8 w-auto grayscale hover:grayscale-0 transition-all">
            <Icon icon="mdi:calendar-star" class="w-full h-full text-primary" />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
@keyframes fade-in-down {
  from {
    opacity: 0;
    transform: translateY(-20px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in-down {
  animation: fade-in-down 0.8s ease-out forwards;
}
</style>