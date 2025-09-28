<script setup>
import { Icon } from '@iconify/vue'
import { ref } from "vue";
const form = ref({
  name: "",
  email: "",
  phone: "",
  carModel: "",
  message: "",
});
const showVideo = ref(false);

const counters = [
  { title: "Live Auction Access", value: "120K" },
  { title: "Vehicle Import", value: "2K" },
  { title: "Reconditioned Vehicles", value: "10K" },
  { title: "Car Dealer Services", value: "40" },
];
const features = [
    {
        icon: 'mdi:car',
        title: 'SUPER FAST',
        text: 'Galley of bled it lorem Ipsum is simply dummy text of the k a to make a type book. but also the leap into electronic typesetting.'
    },
    {
        icon: 'mdi:wallet-outline',
        title: 'AFFORDABLE',
        text: 'Bled it to make a lorem Ipsum is simply dummy text of the k a galley of type book. but also the leap into electronic typesetting.'
    },
    {
        icon: 'mdi:oil',
        title: 'OIL CHANGES',
        text: 'Also the leap into electronic typesetting. lorem Ipsum is simply dummy text of the k a galley of bled it to make a type book but'
    },
    {
        icon: 'mdi:air-conditioner',
        title: 'AIR conditioning',
        text: 'Simply dummy text lorem Ipsum is of the k a galley of bled it to make a type book. but also the leap into electronic typesetting.'
    },
    {
        icon: 'mdi:car-shift-pattern',
        title: 'transmission',
        text: 'But also the leap into electronic typesetting. lorem Ipsum is simply dummy text of the k a galley of bled it to make a type book.'
    },
    {
        icon: 'mdi:deal',
        title: 'DEALERSHIP',
        text: 'Make a type book lorem Ipsum is simply dummy text of the k a galley of bled it to. but also the leap into electronic typesetting.'
    },
]
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
        <div class="absolute inset-0 opacity-[0.5]"></div>
        <div class="relative z-10">
            <div class="pb-12 relative">
                <div
                    class="absolute top-0 left-0 w-64 h-64 bg-primary/5 rounded-full blur-3xl -translate-x-1/2 -translate-y-1/2">
                </div>
                <div
                    class="absolute bottom-0 right-0 w-80 h-80 bg-secondary/5 rounded-full blur-3xl translate-x-1/3 translate-y-1/3">
                </div>
                <div class="text-center mb-16">
                    <div class="relative h-full md:h-96 w-full">
                        <img src="../../public/images/service.jpg" alt="Our Story Background"
                            class="w-full h-full object-cover" />
                        <div class="absolute inset-0 "></div>
                        <div class="absolute inset-0 flex flex-col items-center justify-center text-center px-4 z-10">
                            <h2 class="text-4xl md:text-5xl font-bold text-gray-400 mb-4">
                                Our
                                <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">
                                    Services
                                </span>
                            </h2>
        <p class="text-lg text-white max-w-2xl mx-auto">
                    Get in touch with our team for any inquiries about vehicle auctions, imports, or
                    dealership services.
                  </p>
                        </div>
                    </div>
                </div>
                <section
                    class="w-full relative overflow-hidden py-12 md:py-20 bg-gradient-to-br from-slate-50 via-white to-slate-100">
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

                    <div class="mx-auto px-4 md:px-6 max-w-7xl relative z-10">
                        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                            <div class="text-left">
                                <div class="mb-4 flex items-center">
                                    <div class="h-0.5 w-8 bg-primary mr-3"></div>
                                    <span class="text-sm font-semibold tracking-wider text-primary uppercase">Premium
                                        Vehicle Imports</span>
                                </div>

                                <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 leading-tight mb-6">
                                    Discover Your Dream
                                    <span
                                        class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">Japanese
                                        Vehicle</span>
                                </h1>

                                <p class="text-xl text-gray-600 mb-8 max-w-xl">
                                    Direct access to Japanese auctions with complete import solutions. Quality vehicles,
                                    transparent
                                    pricing, and expert guidance every step of the way.
                                </p>

                                <div class="flex flex-wrap gap-6 mb-8">
                                    <div class="flex items-center">
                                        <div class="bg-primary/10 p-2 rounded-lg mr-3">
                                            <Icon icon="mdi:check-circle" class="w-6 h-6 text-primary" />
                                        </div>
                                        <div>
                                            <div class="text-2xl font-bold text-gray-900">2K+</div>
                                            <div class="text-sm text-gray-500">Vehicles Imported</div>
                                        </div>
                                    </div>
                                    <div class="flex items-center">
                                        <div class="bg-primary/10 p-2 rounded-lg mr-3">
                                            <Icon icon="mdi:check-circle" class="w-6 h-6 text-primary" />
                                        </div>
                                        <div>
                                            <div class="text-2xl font-bold text-gray-900">40+</div>
                                            <div class="text-sm text-gray-500">Car Dealer Services</div>
                                        </div>
                                    </div>
                                </div>

                                <div class="flex flex-wrap gap-4">
                                    <button
                                        class="px-8 py-4 bg-gradient-to-r from-primary to-secondary text-white rounded-xl font-semibold shadow-lg hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1 flex items-center">
                                        <span>Explore Auctions</span>
                                        <Icon icon="mdi:arrow-right" class="ml-2 w-5 h-5" />
                                    </button>
                                </div>
                            </div>

                            <div class="relative">
                                <div
                                    class="rounded-2xl overflow-hidden shadow-2xl border-8 border-white transform rotate-2">
                                    <img src="../../public/images/herovison.jpg" alt="Premium Japanese Vehicle"
                                        class="w-full h-auto object-cover" />
                                </div>

                                <div
                                    class="absolute -top-4 -left-4 bg-white rounded-xl p-4 shadow-lg border border-gray-100 animate-float">
                                    <div class="flex items-center">
                                        <div class="bg-primary/10 p-2 rounded-lg mr-3">
                                            <Icon icon="mdi:gavel" class="w-5 h-5 text-primary" />
                                        </div>
                                        <div>
                                            <div class="font-semibold text-gray-900">Live Auctions</div>
                                            <div class="text-xs text-gray-500">Daily Access</div>
                                        </div>
                                    </div>
                                </div>

                                <!-- Floating card 2 -->
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

                                <!-- Accent element -->
                                <div
                                    class="absolute -bottom-6 -right-6 w-40 h-40 bg-gradient-to-r from-primary to-secondary rounded-2xl shadow-lg -z-10">
                                </div>
                            </div>
                        </div>
                    </div>
                </section>
            </div>
            <section class="w-full py-16 bg-white">
                <div class="max-w-6xl mx-auto grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 px-4">
                    <div v-for="(item, index) in features" :key="index"
                        class="text-center px-6 py-10 border border-gray-200">
                        <Icon :icon="item.icon" class="text-red-500 text-5xl mb-4 mx-auto" />
                        <h3 class="font-bold text-gray-700 text-lg mb-2 uppercase">{{ item.title }}</h3>
                        <p class="text-gray-700 text-sm leading-relaxed">
                            {{ item.text }}
                        </p>
                    </div>
                </div>
            </section>
  <div class="w-full py-16 bg-gradient-to-b from-gray-50 via-white to-gray-100">
    <section
      class="relative min-h-[650px] flex items-center justify-center bg-cover bg-fixed bg-center text-white overflow-hidden"
      style="background-image: url('/images/nissangtr.png')"
    >
      <div
        class="absolute inset-0 bg-gradient-to-r from-primary/35 to-primary/20"
      ></div>
      <div
        class="absolute top-20 left-10 w-6 h-6 rounded-full bg-white/20 animate-float"
      ></div>
      <div
        class="absolute top-40 right-20 w-8 h-8 rounded-full bg-primary/30 animate-float animation-delay-1000"
      ></div>
      <div
        class="absolute bottom-32 left-24 w-5 h-5 rounded-full bg-secondary/30 animate-float animation-delay-2000"
      ></div>

      <UModal v-model="showVideo" size="4xl" title="Watch Video">
        <div
          class="container mx-auto px-6 relative z-10 flex flex-col items-center justify-center text-center"
        >
          <div
            class="flex flex-col items-center justify-center max-w-7xl mx-auto text-center"
          >
            <UButton
              @click="showVideo = true"
              class="group relative w-24 h-24 rounded-full bg-white/20 backdrop-blur-md border-2 border-white/30 flex items-center justify-center shadow-2xl hover:shadow-3xl transition-all duration-500 hover:scale-110"
            >
              <div
                class="absolute inset-0 rounded-full bg-white/20 animate-ping group-hover:animate-none"
              ></div>
              <div
                class="absolute inset-2 rounded-full bg-gradient-to-r from-primary to-secondary"
              ></div>
              <Icon
                icon="heroicons:play-20-solid"
                class="w-10 h-10 text-white relative z-10 ml-1 transition-transform group-hover:scale-110"
              />
            </UButton>

            <h2
              class="text-5xl md:text-6xl lg:text-7xl font-bold text-white mb-6 leading-tight"
            >
              Discover
              <span
                class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary"
                >Exclusive </span
              >
              Vehicle Services
            </h2>
          </div>
        </div>
        <template #body>
          <div class="aspect-video w-full">
            <!-- Only load iframe when modal is open -->
            <iframe
              v-if="showVideo"
              class="w-full h-full rounded-lg"
              src="https://www.youtube.com/embed/dQw4w9WgXcQ?autoplay=1"
              title="YouTube video"
              frameborder="0"
              allow="autoplay; encrypted-media"
              allowfullscreen
            ></iframe>
          </div>
        </template>
      </UModal>
    </section>

    <!-- 2nd Section -->
    <section class="relative -mt-40 overflow-hidden px-6">
      <div
        class="container bg-gradient-to-r from-primary via-primary/90 to-secondary mx-auto px-8 py-12 rounded-3xl shadow-2xl relative z-10 border border-white/20"
      >
        <div
          class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8 text-center"
        >
          <div
            v-for="(counter, index) in counters"
            :key="index"
            class="p-8 bg-gradient-to-r from-primary to-secondary rounded-2xl shadow-lg hover:scale-105 transform transition-all duration-300 border border-white/10 group"
          >
            <!-- Animated counter number -->
            <h3 class="text-5xl md:text-6xl font-bold text-white mb-4">
              {{ counter.value }}+
            </h3>

            <!-- Title with hover effect -->
            <p
              class="text-lg font-semibold text-gray-100 tracking-wide uppercase group-hover:text-white transition-colors"
            >
              {{ counter.title }}
            </p>
          </div>
        </div>
      </div>
    </section>
  </div>
                  <div class="py-16 bg-gradient-to-br from-slate-50 via-white to-slate-100">
        <div class="max-w-5xl mx-auto px-6">
          <!-- Title -->
          <div class="text-center mb-12">
                        <p class="mt-2 text-gray-600">
              This is what we do and we do it perfectly
            </p>
            <h2 class="text-3xl md:text-4xl font-bold text-gray-800">
              Service <span class="text-primary">Form</span>
            </h2>
          </div>

          <div class="bg-white rounded-2xl shadow-xl p-8 md:p-12">
            <form @submit.prevent="handleSubmit" class="grid grid-cols-1 md:grid-cols-2 gap-6">
              <div class="col-span-1">
                <label class="block text-sm font-medium text-gray-700 mb-1">Name</label>
                <div class="relative">
                  <input
                    v-model="form.name"
                    type="text"
                    placeholder="Enter your name"
                    class="w-full pl-2 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-900"
                    required
                  />
                </div>
              </div>

              <div class="col-span-1">
                <label class="block text-sm font-medium text-gray-700 mb-1">Email</label>
                <div class="relative">
                  <input
                    v-model="form.email"
                    type="email"
                    placeholder="Enter your email"
                    class="w-full pl-2 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-900"
                    required
                  />
                </div>
              </div>

              <div class="col-span-1 md:col-span-2">
                <label class="block text-sm font-medium text-gray-700 mb-1">Phone</label>
                <div class="relative">
                  <input
                    v-model="form.phone"
                    type="text"
                    placeholder="Enter your phone"
                    class="w-full pl-2 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-900"
                  />
                </div>
              </div>
              <div class="col-span-1 md:col-span-2">
                <label class="block text-sm font-medium text-gray-700 mb-1">Car Model</label>
                <div class="relative">
                  <select
                    v-model="form.carModel"
                    class="w-full pl-2 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-500"
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
                          <div class="col-span-1 md:col-span-2">
              <label class="block text-sm font-medium text-gray-700 mb-1">Message</label>
              <div class="relative">
                <textarea v-model="form.message" rows="4" placeholder="Write your message"
                  class="w-full pl-2 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-500"></textarea>
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
        </div>
      </div>
        </div>
    </section>
</template>