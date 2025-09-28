<script setup>
const currencyDropdownOpen = ref(false);
const currentCurrency = ref("BDT");
const currencies = ["BDT", "USD", "EUR", "GBP"];
</script>

<template>
  <!-- Modern Top Header Bar -->
  <div class="bg-gray-900 text-gray-100 text-sm py-2.5 border-b border-gray-800">
    <div class="container mx-auto px-4 flex items-center justify-between">
      <!-- Left Side - Info Items -->
      <div class="flex items-center space-x-8">
        <div class="flex items-center gap-2 hover:text-blue-400 transition-colors group">
          <Icon name="ph:phone-light" class="text-lg text-primary group-hover:scale-110 transition-transform" />
          <span>Hotline: <span class="font-medium text-white">09613 787878</span></span>
        </div>

        <div class="flex items-center gap-2 hover:text-blue-400 transition-colors group">
          <Icon name="mdi:map-marker-outline" class="text-lg text-primary group-hover:scale-110 transition-transform" />
          <span>Showroom: <span class="font-medium text-white">Gulshan-1, Dhaka</span></span>
        </div>

        <div class="flex items-center gap-2 hover:text-blue-400 transition-colors group">
          <Icon name="mdi:clock-outline" class="text-lg text-primary group-hover:scale-110 transition-transform" />
          <span>Working Hours: <span class="font-medium text-white">9AM - 11PM</span></span>
        </div>
      </div>

      <!-- Right Side - Actions -->
      <div class="flex items-center space-x-5">
        <!-- Social Icons -->
        <div class="flex items-center space-x-4">
          <a href="#" class="text-primary hover:text-blue-400 transition-colors" aria-label="Facebook">
            <Icon name="mdi:facebook" class="text-lg hover:scale-110 transition-transform" />
          </a>
          <a href="#" class="text-primary hover:text-pink-400 transition-colors" aria-label="Instagram">
            <Icon name="mdi:instagram" class="text-lg hover:scale-110 transition-transform" />
          </a>
          <a href="#" class="text-primary hover:text-blue-400 transition-colors" aria-label="Twitter">
            <Icon name="mdi:twitter" class="text-lg hover:scale-110 transition-transform" />
          </a>
          <a href="#" class="text-primary hover:text-red-400 transition-colors" aria-label="YouTube">
            <Icon name="mdi:youtube" class="text-lg hover:scale-110 transition-transform" />
          </a>
        </div>

        <!-- Divider -->
        <div class="h-5 w-px bg-gray-700"></div>

        <!-- Currency Selector -->
        <div class="relative">
          <button
            @click="currencyDropdownOpen = !currencyDropdownOpen"
            @blur="currencyDropdownOpen = false"
            class="flex items-center gap-1 px-3 py-1 rounded-md hover:bg-gray-800 transition-colors group"
          >
            <span class="font-medium">{{ currentCurrency }}</span>
            <Icon
              name="mdi:chevron-down"
              class="text-lg transition-transform duration-200 text-primary"
              :class="{ 'rotate-180': currencyDropdownOpen }"
            />
          </button>

          <transition name="dropdown">
            <div
              v-if="currencyDropdownOpen"
              class="absolute right-0 mt-2 w-32 bg-gray-800 text-gray-100 rounded-lg shadow-xl z-50 border border-gray-700 overflow-hidden"
            >
              <button
                v-for="currency in currencies"
                :key="currency"
                @click="currentCurrency = currency"
                class="block w-full text-left px-4 py-2.5 text-sm hover:bg-gray-700 transition-colors flex items-center"
                :class="{ 'text-white': currentCurrency === currency }"
              >
                {{ currency }}
                <Icon 
                  name="mdi:check" 
                  class="ml-auto text-primary" 
                  v-if="currentCurrency === currency"
                />
              </button>
            </div>
          </transition>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.dropdown-enter-active,
.dropdown-leave-active {
  transition: all 0.15s cubic-bezier(0.4, 0, 0.2, 1);
}
.dropdown-enter-from,
.dropdown-leave-to {
  opacity: 0;
  transform: translateY(-8px);
}
</style>