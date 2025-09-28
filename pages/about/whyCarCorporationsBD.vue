<script setup>
import { Icon } from "@iconify/vue";
const whyChooseUs = [
  {
    icon: 'mdi:shield-check-outline',
    title: 'Trusted & Transparent',
    description: 'We pride ourselves on transparency. All vehicles come with verified auction sheets and detailed inspection reports.'
  },
  {
    icon: 'mdi:account-group-outline',
    title: 'Expert Guidance',
    description: 'Our experienced team provides professional guidance throughout the auction and import process, ensuring a smooth experience.'
  },
  {
    icon: 'mdi:currency-usd',
    title: 'Competitive Pricing',
    description: 'By providing direct access to auctions, we cut out the middleman, offering you the best possible prices for your dream car.'
  },
  {
    icon: 'mdi:headset',
    title: 'End-to-End Support',
    description: 'From bidding to delivery, we offer comprehensive support, including logistics, customs clearance, and after-sales service.'
  }
];

</script>

<template>
  <section class="w-full relative overflow-hidden bg-gradient-to-br from-slate-50 via-white to-slate-100">
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
      <div class="relative">
        <div
          class="absolute top-0 left-0 w-64 h-64 bg-primary/5 rounded-full blur-3xl -translate-x-1/2 -translate-y-1/2">
        </div>
        <div
          class="absolute bottom-0 right-0 w-80 h-80 bg-secondary/5 rounded-full blur-3xl translate-x-1/3 translate-y-1/3">
        </div>
        <div class="relative z-10">
          <div class="text-center mb-16">
            <section class="relative bg-gradient-to-br from-slate-50 via-white to-slate-100">
              <div class="relative h-[500px] md:h-[600px] w-full">
                <img src="../../public/images/herovison.jpg" alt="Our Story Background"
                  class="w-full h-full object-cover" />
                <div class="absolute inset-0 "></div>
                <div class="absolute inset-0 flex flex-col items-center justify-center text-center px-4 z-10">
                  <h2 class="text-4xl md:text-5xl font-bold text-gray-100 mb-4">
                    Why Car 
                    <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">
                      Corporations BD
                    </span>
                  </h2>
                  <p class="text-xl text-gray-100 max-w-2xl">
                    Where every expense becomes a brushstroke of intention, creating a masterpiece of financial
                    well-being and wealth.
                  </p>
                </div>
              </div>
              <div class="relative -mt-30 z-20">
                <div class="max-w-7xl mx-auto px-4">
                  <div
                    class="bg-white rounded-3xl shadow-xl p-6 md:p-10 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 md:gap-8">
                    <div
                      class="group text-start rounded-2xl p-4 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-primary/20 hover:-translate-y-2 relative overflow-hidden">
                      <div
                        class="absolute top-0 right-0 w-20 h-20 bg-primary/5 rounded-bl-full transition-all duration-500 group-hover:bg-primary/10">
                      </div>
                      <div class="flex justify-start mb-5 relative z-10">
                        <div
                          class="p-3 bg-gradient-to-br from-primary/10 to-primary/5 rounded-xl transition-colors duration-500 group-hover:from-primary/15 group-hover:to-primary/10 shadow-sm">
                          <Icon icon="mdi:gavel" class="w-7 h-7 text-primary" />
                        </div>
                      </div>
                      <h3 class="font-semibold text-xl text-gray-900 mb-2 relative z-10">Live Auction Access</h3>
                      <span
                        class="text-primary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0 relative z-10">Explore
                        auctions</span>
                    </div>
                    <div
                      class="group text-start rounded-2xl p-4 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-secondary/20 hover:-translate-y-2 relative overflow-hidden">
                      <div
                        class="absolute top-0 right-0 w-20 h-20 bg-secondary/5 rounded-bl-full transition-all duration-500 group-hover:bg-secondary/10">
                      </div>
                      <div class="flex justify-start mb-5 relative z-10">
                        <div
                          class="p-3 bg-gradient-to-br from-secondary/10 to-secondary/5 rounded-xl transition-colors duration-500 group-hover:from-secondary/15 group-hover:to-secondary/10 shadow-sm">
                          <Icon icon="mdi:truck-delivery" class="w-7 h-7 text-secondary" />
                        </div>
                      </div>
                      <h3 class="font-semibold text-xl text-gray-900 mb-2 relative z-10">Vehicle Import</h3>
                      <span
                        class="text-secondary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0 relative z-10">Import
                        process</span>
                    </div>
                    <div
                      class="group text-start rounded-2xl p-4 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-primary/20 hover:-translate-y-2 relative overflow-hidden">
                      <div
                        class="absolute top-0 right-0 w-20 h-20 bg-primary/5 rounded-bl-full transition-all duration-500 group-hover:bg-primary/10">
                      </div>
                      <div class="flex justify-start mb-5 relative z-10">
                        <div
                          class="p-3 bg-gradient-to-br from-primary/10 to-primary/5 rounded-xl transition-colors duration-500 group-hover:from-primary/15 group-hover:to-primary/10 shadow-sm">
                          <Icon icon="mdi:car-wrench" class="w-7 h-7 text-primary" />
                        </div>
                      </div>
                      <h3 class="font-semibold text-xl text-gray-900 mb-2 relative z-10">Quality Vehicles</h3>
                      <span
                        class="text-primary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0 relative z-10">View
                        inventory</span>
                    </div>
                    <div
                      class="group text-start rounded-2xl p-4 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-secondary/20 hover:-translate-y-2 relative overflow-hidden">
                      <div
                        class="absolute top-0 right-0 w-20 h-20 bg-secondary/5 rounded-bl-full transition-all duration-500 group-hover:bg-secondary/10">
                      </div>
                      <div class="flex justify-start mb-5 relative z-10">
                        <div
                          class="p-3 bg-gradient-to-br from-secondary/10 to-secondary/5 rounded-xl transition-colors duration-500 group-hover:from-secondary/15 group-hover:to-secondary/10 shadow-sm">
                          <Icon icon="mdi:storefront" class="w-7 h-7 text-secondary" />
                        </div>
                      </div>
                      <h3 class="font-semibold text-xl text-gray-900 mb-2 relative z-10">Dealer Services</h3>
                      <span
                        class="text-secondary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0 relative z-10">Our
                        services</span>
                    </div>
                  </div>
                </div>
              </div>
            </section>
            <section class="py-16">
                <div class="max-w-7xl mx-auto px-4">
                    <div class="text-center mb-12">
                        <h2 class="text-3xl md:text-4xl font-bold text-gray-800">Why Choose Car Corporations BD</h2>
                        <p class="text-lg text-gray-600 mt-4 max-w-3xl mx-auto">Your trusted partner for importing high-quality vehicles directly from Japan.</p>
                    </div>
                    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
                        <div v-for="(item, index) in whyChooseUs" :key="index" class="bg-white rounded-2xl p-8 shadow-lg hover:shadow-2xl transition-shadow duration-300 transform hover:-translate-y-2">
                            <div class="flex items-center justify-center h-16 w-16 rounded-full bg-primary/10 mb-6">
                                <Icon :icon="item.icon" class="h-8 w-8 text-primary" />
                            </div>
                            <h3 class="text-xl font-semibold text-gray-900 mb-3">{{ item.title }}</h3>
                            <p class="text-gray-600">{{ item.description }}</p>
                        </div>
                    </div>
                </div>
            </section>
          </div>
          <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
            <div class="relative">
              <div class="rounded-2xl overflow-hidden shadow-xl border-4 border-white">
                <img src="../../public/images/vison1.jpg" alt="Our Story" class="w-full h-full object-cover" />
              </div>
              <div
                class="absolute -bottom-6 -right-6 w-40 h-40 bg-gradient-to-r from-primary to-secondary rounded-2xl shadow-lg -z-10">
              </div>
            </div>
            <div>
              <div class="mb-4 flex items-center justify-center">
                <div class="h-0.5 w-8 bg-primary mr-3"></div>
                <span class="text-sm font-semibold tracking-wider text-primary uppercase">Our Journey</span>
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
                    <h4 class="font-semibold text-gray-900 mb-1">Our Mission</h4>
                    <p class="text-gray-600 text-sm">
                      To democratize access to international vehicle auctions and provide transparent, reliable import
                      services.
                    </p>
                  </div>
                </div>

                <div class="flex items-start">
                  <div class="bg-secondary/10 p-2 rounded-lg mr-4 flex-shrink-0">
                    <Icon icon="mdi:eye-outline" class="w-6 h-6 text-secondary" />
                  </div>
                  <div>
                    <h4 class="font-semibold text-gray-900 mb-1">Our Vision</h4>
                    <p class="text-gray-600 text-sm">
                      To become Bangladesh's most trusted partner for vehicle imports and auction services.
                    </p>
                  </div>
                </div>
              </div>

              <div class="flex gap-4">
                <div class="bg-gray-50 rounded-lg px-4 py-3">
                  <div class="text-2xl font-bold text-primary">120K+</div>
                  <div class="text-sm text-gray-500">Live Auction Access</div>
                </div>
                <div class="bg-gray-50 rounded-lg px-4 py-3">
                  <div class="text-2xl font-bold text-primary">10K+</div>
                  <div class="text-sm text-gray-500">Reconditioned Vehicles</div>
                </div>
              </div>

              <button
                class="mt-8 px-6 py-3 bg-gradient-to-r from-primary to-secondary text-white rounded-lg font-medium shadow-lg hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1 flex items-center">
                <span>Read Full Story</span>
                <Icon icon="mdi:arrow-right" class="ml-2 w-5 h-5" />
              </button>
            </div>
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
                <span class="text-sm font-semibold tracking-wider text-primary uppercase">Premium Vehicle Imports</span>
              </div>

              <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 leading-tight mb-6">
                Discover Your Dream
                <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">Japanese
                  Vehicle</span>
              </h1>

              <p class="text-xl text-gray-600 mb-8 max-w-xl">
                Direct access to Japanese auctions with complete import solutions. Quality vehicles, transparent
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
              <div class="rounded-2xl overflow-hidden shadow-2xl border-8 border-white transform rotate-2">
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
      </section>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 md:gap-8">
        <div
          class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-primary/20 hover:-translate-y-2 relative overflow-hidden">
          <div
            class="absolute top-0 right-0 w-28 h-28 bg-primary/5 rounded-bl-full transition-all duration-500 group-hover:bg-primary/10">
          </div>
          <div class="flex justify-start mb-5 relative z-10">
            <div
              class="p-3 bg-gradient-to-br from-primary/10 to-primary/5 rounded-xl transition-colors duration-500 group-hover:from-primary/15 group-hover:to-primary/10 shadow-sm">
              <Icon icon="mdi:gavel" class="w-7 h-7 text-primary" />
            </div>
          </div>
          <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
            Live Auction Access
          </h3>
          <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
            Real-time bidding access to Japanese auctions with expert assistance and market insights.
          </p>
          <div class="flex items-center relative z-10">
            <div
              class="w-8 h-8 rounded-full bg-primary/5 flex items-center justify-center transition-colors duration-300 group-hover:bg-primary/10">
              <Icon icon="mdi:arrow-right"
                class="text-primary transition-all duration-500 transform group-hover:translate-x-1" />
            </div>
            <span
              class="text-primary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0">Explore
              auctions</span>
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
              <Icon icon="mdi:truck-delivery" class="w-7 h-7 text-secondary" />
            </div>
          </div>
          <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
            Vehicle Import
          </h3>
          <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
            Complete import solutions with customs clearance, documentation, and logistics handled by experts.
          </p>
          <div class="flex items-center relative z-10">
            <div
              class="w-8 h-8 rounded-full bg-secondary/5 flex items-center justify-center transition-colors duration-300 group-hover:bg-secondary/10">
              <Icon icon="mdi:arrow-right"
                class="text-secondary transition-all duration-500 transform group-hover:translate-x-1" />
            </div>
            <span
              class="text-secondary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0">Import
              process</span>
          </div>
        </div>

        <!-- Card 3: Reconditioned Vehicles -->
        <div
          class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-primary/20 hover:-translate-y-2 relative overflow-hidden">
          <div
            class="absolute top-0 right-0 w-28 h-28 bg-primary/5 rounded-bl-full transition-all duration-500 group-hover:bg-primary/10">
          </div>
          <div class="flex justify-start mb-5 relative z-10">
            <div
              class="p-3 bg-gradient-to-br from-primary/10 to-primary/5 rounded-xl transition-colors duration-500 group-hover:from-primary/15 group-hover:to-primary/10 shadow-sm">
              <Icon icon="mdi:car-wrench" class="w-7 h-7 text-primary" />
            </div>
          </div>
          <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
            Quality Vehicles
          </h3>
          <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
            Thoroughly inspected and reconditioned vehicles with detailed history reports and quality guarantees.
          </p>
          <div class="flex items-center relative z-10">
            <div
              class="w-8 h-8 rounded-full bg-primary/5 flex items-center justify-center transition-colors duration-300 group-hover:bg-primary/10">
              <Icon icon="mdi:arrow-right"
                class="text-primary transition-all duration-500 transform group-hover:translate-x-1" />
            </div>
            <span
              class="text-primary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0">View
              inventory</span>
          </div>
        </div>

        <!-- Card 4: Car Dealer Services -->
        <div
          class="group text-start bg-white rounded-2xl p-6 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-secondary/20 hover:-translate-y-2 relative overflow-hidden">
          <div
            class="absolute top-0 right-0 w-28 h-28 bg-secondary/5 rounded-bl-full transition-all duration-500 group-hover:bg-secondary/10">
          </div>
          <div class="flex justify-start mb-5 relative z-10">
            <div
              class="p-3 bg-gradient-to-br from-secondary/10 to-secondary/5 rounded-xl transition-colors duration-500 group-hover:from-secondary/15 group-hover:to-secondary/10 shadow-sm">
              <Icon icon="mdi:storefront" class="w-7 h-7 text-secondary" />
            </div>
          </div>
          <h3 class="font-semibold text-xl text-gray-900 mb-3 relative z-10">
            Dealer Services
          </h3>
          <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
            Comprehensive dealership support including financing options, warranty packages, and after-sales service.
          </p>
          <div class="flex items-center relative z-10">
            <div
              class="w-8 h-8 rounded-full bg-secondary/5 flex items-center justify-center transition-colors duration-300 group-hover:bg-secondary/10">
              <Icon icon="mdi:arrow-right"
                class="text-secondary transition-all duration-500 transform group-hover:translate-x-1" />
            </div>
            <span
              class="text-secondary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0">Our
              services</span>
          </div>
        </div>
      </div>
    </div>
    <div>
      <HomeBrandSection/>
    </div>
      <div class="mt-4 py-8">
      </div>
      <div class="mt-16 pt-12 border-t border-gray-200">
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