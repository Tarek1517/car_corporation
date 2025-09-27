<script setup>
import { Icon } from "@iconify/vue";
</script>

<template>
  <section class="w-full relative overflow-hidden py-2 md:py-6 bg-gradient-to-br from-slate-50 via-white to-slate-100">
    <div
      class="absolute top-0 right-0 w-96 h-96 bg-primary/10 rounded-full -translate-y-1/3 translate-x-1/3 blur-3xl animate-pulse-slow">
    </div>
    <div
      class="absolute bottom-0 left-0 w-[32rem] h-[32rem] bg-secondary/10 rounded-full translate-y-1/3 -translate-x-1/3 blur-3xl animate-pulse-slow delay-1000">
    </div>
    <div class="absolute top-1/2 left-1/4 w-64 h-64 bg-primary/5 rounded-full blur-3xl animate-pulse-slow delay-500">
    </div>
    <div class="absolute inset-0 opacity-[0.03] bg-grid-pattern"></div>
    <div class="container mx-auto px-4">
      <h2 class="text-3xl md:text-4xl font-extrabold text-gray-900 text-center mb-8 md:mb-12">
        Happy Customer Car Corporations BD
      </h2>
    </div>

    <div class="">
      <div class="flex items-center justify-center">
        <img src="../../public/images/car-yellow.png" class="h-full w-full" alt="Happy Customer Car">
      </div>
    </div>

    <div class="container mx-auto px-4 pb-12">
      <div
        class="max-w-7xl mx-auto group text-start bg-white transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-primary/20 hover:-translate-y-2 relative overflow-hidden rounded-xl">
        <div
          class="absolute top-0 right-0 w-28 h-28 bg-primary/5 rounded-bl-full transition-all duration-500 group-hover:bg-primary/10">
        </div>
        <div class="p-6 relative z-10">
          <h3 class="font-semibold text-xl text-gray-900 mb-4">Customer Information</h3>
          <div class="space-y-4">
            <div class="flex items-start">
              <div class="flex-shrink-0 mt-1">
                <div class="w-8 h-8 rounded-full bg-primary/10 flex items-center justify-center">
                  <Icon icon="mdi:account" class="w-4 h-4 text-primary" />
                </div>
              </div>
              <div class="ml-3">
                <p class="text-sm font-medium text-gray-900">Md. Rahman</p>
                <p class="text-xs text-gray-500">Customer ID: #HC-2023-0842</p>
              </div>
            </div>

            <div class="flex items-start">
              <div class="flex-shrink-0 mt-1">
                <div class="w-8 h-8 rounded-full bg-primary/10 flex items-center justify-center">
                  <Icon icon="mdi:phone" class="w-4 h-4 text-primary" />
                </div>
              </div>
              <div class="ml-3">
                <p class="text-sm text-gray-900">+880 1712-345678</p>
                <p class="text-xs text-gray-500">Primary Contact</p>
              </div>
            </div>

            <div class="flex items-start">
              <div class="flex-shrink-0 mt-1">
                <div class="w-8 h-8 rounded-full bg-primary/10 flex items-center justify-center">
                  <Icon icon="mdi:map-marker" class="w-4 h-4 text-primary" />
                </div>
              </div>
              <div class="ml-3">
                <p class="text-sm text-gray-900">123 Gulshan Avenue, Dhaka-1212</p>
                <p class="text-xs text-gray-500">Permanent Address</p>
              </div>
            </div>
          </div>
          <div class="mt-6 pt-4 border-t border-gray-100">
            <div class="flex justify-between items-center">
              <span class="text-xs text-gray-500">Member Since</span>
              <span class="text-sm font-medium text-gray-900">Jan 2020</span>
            </div>
            <div class="flex justify-between items-center mt-2">
              <span class="text-xs text-gray-500">Last Purchase</span>
              <span class="text-sm font-medium text-gray-900">15 Aug 2023</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>