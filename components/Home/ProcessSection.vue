<script setup>
import { useRouter } from 'vue-router'
const router = useRouter();
const goToServices = () => {
  router.push('/services')
}
const goToContacts = () => {
  router.push('/contact-us/contact')
}
const goToCarAuction = () => {
  router.push('/carAuction')
}
const goToVehicleImport = () => {
  router.push('/vehicleImport')
}
const goToReconditionedVehicles = () => {
  router.push('/reconditionedVehicles')
}
const goToServicesPage = () => {
  router.push('/carDealerService')
}
</script>

<template>
  <section
    class="w-full relative overflow-hidden py-28 bg-gradient-to-br from-slate-50 via-white to-slate-100"
  >
    <!-- Animated background elements -->
    <div
      class="absolute top-0 right-0 w-96 h-96 bg-primary/5 rounded-full -translate-y-1/3 translate-x-1/3 blur-3xl animate-pulse-slow"
    ></div>
    <div
      class="absolute bottom-0 left-0 w-[32rem] h-[32rem] bg-secondary/5 rounded-full translate-y-1/3 -translate-x-1/3 blur-3xl animate-pulse-slow delay-1000"
    ></div>

    <!-- Geometric pattern overlay -->
    <div class="absolute inset-0 opacity-[0.03] bg-geometric-pattern"></div>

    <div class="container mx-auto px-6 relative z-10">
      <!-- Heading -->
      <div
        class="flex flex-col md:flex-row text-start mb-20 gap-12 items-center"
      >
        <div class="md:w-1/2">
          <div class="mb-4 flex items-center">
            <div class="h-0.5 w-8 bg-primary mr-3"></div>
            <span
              class="text-sm font-semibold tracking-wider text-primary uppercase"
              >Our Services</span
            >
          </div>
          <h2
            class="text-5xl md:text-6xl font-bold text-gray-900 leading-tight mb-6"
          >
            Premium Solutions For
            <span
              class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary"
              >Vehicle Auctions</span
            >
          </h2>
          <p class="text-gray-600 text-lg leading-relaxed max-w-xl">
            Direct access to global auctions with seamless import processes and
            premium vehicle selection.
          </p>
        </div>
        <div class="md:w-1/2">
          <p class="text-gray-600 text-lg leading-relaxed">
            Car Corporations BD is a LIVE AUCTION AGENT / IMPORTER / CAR DEALER
            of reconditioned & brand-new vehicles from all over the world,
            especially from Japan. We offer clients direct access to AUCTION for
            purchasing their desired cars.
          </p>
          <div class="flex gap-4 mt-8">
            <button
            @click="goToServices"
              class="px-6 py-3 bg-gradient-to-r from-primary to-secondary text-white rounded-lg font-medium shadow-md hover:shadow-lg transition-all duration-300 transform hover:-translate-y-0.5 cursor-pointer"
            >
              Explore Services
            </button>
            <button
            @click="goToContacts"
              class="px-6 py-3 border border-primary/55 text-gray-700 rounded-lg font-medium hover:border-primary/50 transition-colors duration-300 hover:bg-primary/5 cursor-pointer"
            >
              Contact Us
            </button>
          </div>
        </div>
      </div>

      <!-- Services -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
        <!-- Card 1: Live Auction Access -->
        <div
          class="group text-start bg-white rounded-2xl p-8 transition-all duration-500 hover:shadow-sm shadow-2xl border hover:border-gray-100 border-primary/30 hover:translate-y-1 -translate-y-3 relative overflow-hidden"
        >
          <div
            class="absolute top-0 right-0 w-28 h-28 bg-primary/10 rounded-bl-full transition-all duration-500"
          ></div>
          <div class="flex justify-start mb-6 relative z-10">
            <div
              class="p-4 bg-gradient-to-br from-primary/15 to-primary/10 rounded-xl transition-colors duration-500 shadow-sm"
            >
              <Icon name="mdi:gavel" class="w-8 h-8 text-primary text-3xl" />
            </div>
          </div>
          <h3 class="font-semibold text-xl text-gray-900 mb-4 relative z-10">
            Live Auction Access
          </h3>
          <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
            Get direct access to live vehicle auctions in Japan and around the
            world to bid on your desired cars.
          </p>
          <div class="flex items-center relative z-10">
            <div
              class="w-8 h-8 rounded-full bg-secondary/10 flex items-center justify-center transition-colors duration-300 group-hover:bg-primary/10"
            >
              <Icon
                name="mdi:arrow-right"
                class="text-secondary transition-all duration-500 transform group-hover:text-primary group-hover:translate-x-1 cursor-pointer"
              />
            </div>
            <span @click="goToCarAuction"
              class="text-primary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-0 opacity-100  hover:opacity-100 cursor-pointer">
              Learn more
              </span>
          </div>
        </div>

        <div
          class="group text-start bg-white rounded-2xl p-8 transition-all duration-500 shadow-sm hover:shadow-2xl border border-gray-100 hover:border-secondary/30 hover:-translate-y-3 relative overflow-hidden"
        >
          <div
            class="absolute top-0 right-0 w-28 h-28 bg-secondary/10 rounded-bl-full transition-all duration-500"
          ></div>
          <div class="flex justify-start mb-6 relative z-10">
            <div
              class="p-4 bg-gradient-to-br from-secondary/15 to-secondary/10 rounded-xl transition-colors duration-500 shadow-sm"
            >
              <Icon
                name="mdi:truck-delivery"
                class="w-8 h-8 text-secondary text-3xl"
              />
            </div>
          </div>
          <h3 class="font-semibold text-xl text-gray-900 mb-4 relative z-10">
            Vehicle Import
          </h3>
          <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
            We handle import procedures to bring reconditioned or brand-new
            vehicles from Japan directly to Bangladesh.
          </p>
          <div class="flex items-center relative z-10">
            <div
              class="w-8 h-8 rounded-full bg-primary/10 flex items-center justify-center transition-colors duration-300 group-hover:bg-secondary/10"
            >
              <Icon
                name="mdi:arrow-right"
                class="text-primary transition-all duration-500 transform group-hover:text-secondary group-hover:translate-x-1"
              />
            </div>
            <span @click="goToVehicleImport"
              class="text-secondary text-sm font-medium transition-all duration-300 ml-3 opacity-0 group-hover:opacity-100 cursor-pointer"
              >Learn more</span
            >
          </div>
        </div>

        <div
          class="group text-start bg-white rounded-2xl p-8 transition-all duration-500 hover:shadow-sm shadow-2xl border hover:border-gray-100 border-primary/30 hover:translate-y-1 -translate-y-3 relative overflow-hidden"
        >
          <div
            class="absolute top-0 right-0 w-28 h-28 bg-primary/10 rounded-bl-full transition-all duration-500"
          ></div>
          <div class="flex justify-start mb-6 relative z-10">
            <div
              class="p-4 bg-gradient-to-br from-primary/15 to-primary/10 rounded-xl transition-colors duration-500 shadow-sm"
            >
              <Icon
                name="mdi:car-wrench"
                class="w-8 h-8 text-primary text-3xl"
              />
            </div>
          </div>
          <h3 class="font-semibold text-xl text-gray-900 mb-4 relative z-10">
            Reconditioned Vehicles
          </h3>
          <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
            Choose from a wide range of inspected and fully reconditioned
            vehicles, ensuring quality and reliability.
          </p>
          <div class="flex items-center relative z-10">
            <div
              class="w-8 h-8 rounded-full bg-secondary/10 flex items-center justify-center transition-colors duration-300 group-hover:bg-primary/10"
            >
              <Icon
                name="mdi:arrow-right"
                class="text-secondary transition-all duration-500 transform group-hover:text-primary group-hover:translate-x-1"
              />
            </div>
            <span @click="goToReconditionedVehicles"
              class="text-primary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-0 opacity-100 hover:opacity-100 cursor-pointer"
              >Learn more</span
            >
          </div>
        </div>

        <!-- Card 4: Car Dealer Services -->
        <div
          class="group text-start bg-white rounded-2xl p-8 transition-all duration-500 shadow-sm hover:shadow-2xl border border-gray-100 hover:border-secondary/30 hover:-translate-y-3 relative overflow-hidden"
        >
          <div
            class="absolute top-0 right-0 w-28 h-28 bg-secondary/10 rounded-bl-full transition-all duration-500"
          ></div>
          <div class="flex justify-start mb-6 relative z-10">
            <div
              class="p-4 bg-gradient-to-br from-secondary/15 to-secondary/10 rounded-xl transition-colors duration-500 shadow-sm"
            >
              <Icon
                name="mdi:storefront"
                class="w-8 h-8 text-secondary text-3xl"
              />
            </div>
          </div>
          <h3 class="font-semibold text-xl text-gray-900 mb-4 relative z-10">
            Car Dealer Services
          </h3>
          <p class="text-gray-500 text-sm leading-relaxed mb-6 relative z-10">
            We provide professional dealership services including pricing
            advice, negotiation, and after-sales support.
          </p>
          <div class="flex items-center relative z-10">
            <div
              class="w-8 h-8 rounded-full bg-primary/10 flex items-center justify-center transition-colors duration-300 group-hover:bg-secondary/10"
            >
              <Icon
                name="mdi:arrow-right"
                class="text-primary transition-all duration-500 transform group-hover:text-secondary group-hover:translate-x-1"
              />
            </div>
            <span @click="goToServicesPage"
              class="text-secondary text-sm font-medium transition-all duration-300 ml-3 opacity-0 group-hover:opacity-100 cursor-pointer"
              >Learn more</span
            >
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style>
@keyframes pulse-slow {
  0%,
  100% {
    opacity: 0.5;
  }
  50% {
    opacity: 0.8;
  }
}

.animate-pulse-slow {
  animation: pulse-slow 8s cubic-bezier(0.4, 0, 0.6, 1) infinite;
}

.bg-geometric-pattern {
  background-image: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23000000' fill-opacity='0.05'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
}
</style>

