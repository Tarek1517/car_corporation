<script setup>
const activeMenu = ref(null);
const searchQuery = ref("");

const menus = [
  {
    title: "New Cars",
    items: [
      { title: "Sedan", icon: "mdi:sedan" },
      { title: "SUV", icon: "mdi:suv" },
      { title: "Hybrid", icon: "mdi:hybrid" },
      { title: "Electric", icon: "mdi:car-electric" },
    ],
  },
  {
    title: "Used Cars",
    items: [
      { title: "Budget (Under 5L)", icon: "mdi:cash-100" },
      { title: "Premium (5L-15L)", icon: "mdi:currency-usd-circle" },
      { title: "Luxury (15L+)", icon: "mdi:diamond-stone" },
      { title: "Certified Pre-Owned", icon: "mdi:certificate" },
    ],
  },
  {
    title: "Services",
    items: [
      { title: "Car Financing", icon: "mdi:finance", to:"/carFinalice/carMoney" },
      { title: "Insurance", icon: "mdi:shield-check", to:"/Inssurance/inssurance" },
      { title: "Inspection", icon: "mdi:clipboard-check", to:"Incpection/incpection" },
      { title: "Shipping", icon: "mdi:truck-delivery" },
    ],
  },
  {
    title: "About Us",
    items: [
      { title: "Our Story", icon: "mdi:book-open", to:"/about/our-story" },
      { title: "Showrooms", icon: "mdi:storefront", to:"/showrooms/showrooms" },
      { title: "Testimonials", icon: "mdi:message-text", to:"/testimonial/testimonial" },
      { title: "Contact Us", icon: "mdi:phone", to:"/contact-us/contact" },
    ],
  },
];
</script>

<template>
  <header
    class="sticky top-0 z-40 bg-white/95 backdrop-blur-md border-b border-gray-100 shadow-sm"
  >
    <div class="container mx-auto px-3">
      <div class="flex items-center justify-between h-20">
        <!-- Logo -->
        <NuxtLink to="/" class="flex items-center group relative">
          <img
            src="/images/logo.jpg"
            alt="CarCorporation BD"
            class="h-auto w-12 rounded-full"
          />
        </NuxtLink>

        <!-- Desktop Menu -->
        <nav class="hidden lg:flex items-center space-x-1">
          <div
            v-for="(menu, index) in menus"
            :key="index"
            @mouseenter="activeMenu = index"
            @mouseleave="activeMenu = null"
            class="relative"
          >
            <button
              class="px-5 py-2 text-gray-800 font-medium hover:text-primary transition flex items-center group relative"
            >
              <span class="relative z-10">{{ menu.title }}</span>
              <span
                class="absolute bottom-0 left-1/2 w-0 h-0.5 bg-primary transform -translate-x-1/2 transition-all duration-300 group-hover:w-4/5"
              ></span>
              <Icon
                name="mdi:chevron-down"
                class="ml-1.5 text-gray-400 text-lg transition-transform duration-200 group-hover:rotate-180 group-hover:text-primary"
              />
            </button>

            <!-- Modern Dropdown Menu -->
            <transition name="dropdown">
              <div
                v-if="activeMenu === index"
                class="absolute left-1/2 transform -translate-x-1/2 mt-3 w-64 bg-white rounded-xl shadow-2xl z-50 overflow-hidden border border-gray-100"
              >
                <div class="py-2">
                  <NuxtLink
                    v-for="(item, i) in menu.items"
                    :key="i"
                    :to="item.to || '#'"
                    class="px-5 py-3 flex items-center text-gray-700 hover:bg-gray-50 hover:text-primary transition-all duration-200 group"
                  >
                    <Icon
                      :name="item.icon"
                      class="mr-3 text-primary text-lg group-hover:scale-110 transition-transform"
                    />
                    <span class="font-medium">{{ item.title }}</span>
                    <Icon
                      name="mdi:chevron-right"
                      class="ml-auto text-gray-300 group-hover:text-primary transition-colors"
                    />
                  </NuxtLink>
                </div>
              </div>
            </transition>
          </div>
        </nav>

        <!-- Search + CTA -->
        <div class="flex items-center space-x-4">
          <!-- Search Bar -->
          <div class="relative hidden md:block">
            <div class="relative group">
              <input
                v-model="searchQuery"
                type="text"
                placeholder="Find cars, parts & more..."
                class="pl-12 pr-5 py-3 border-0 bg-gray-50 rounded-full focus:ring-2 focus:ring-primary/50 focus:bg-white w-56 transition-all duration-300 group-hover:w-64 focus:w-64 shadow-inner"
              />
              <div
                class="absolute inset-y-0 left-0 flex items-center pl-4 pointer-events-none"
              >
                <Icon
                  name="mdi:magnify"
                  class="text-xl text-gray-500 group-hover:text-primary transition-colors"
                />
              </div>
              <button
                v-if="searchQuery"
                @click="searchQuery = ''"
                class="absolute right-3 top-1/2 transform -translate-y-1/2 text-gray-400 hover:text-primary transition-colors"
              >
                <Icon name="mdi:close" class="text-lg" />
              </button>
            </div>
          </div>

          <!-- CTA Button -->
          <NuxtLink
            to="#"
            class="hidden xl:flex items-center px-4 py-2 bg-gradient-to-r from-primary to-secondary text-white font-medium rounded-full shadow-lg hover:shadow-xl transition-all hover:scale-[1.02] group"
          >
            <Icon
              name="material-symbols:account-circle"
              class="mr-2 text-lg group-hover:scale-110 transition-transform"
            />
            <span>Login</span>
          </NuxtLink>

          <!-- Mobile Menu Toggle -->
          <button
            class="lg:hidden p-2 rounded-full bg-gray-50 hover:bg-gray-100 transition-colors"
          >
            <Icon name="mdi:menu" class="text-2xl text-gray-700" />
          </button>
        </div>
      </div>
    </div>
  </header>
</template>

<style scoped>
.dropdown-enter-active,
.dropdown-leave-active {
  transition: all 0.2s cubic-bezier(0.4, 0, 0.2, 1);
}
.dropdown-enter-from,
.dropdown-leave-to {
  opacity: 0;
  transform: translateY(-10px) translateX(-50%);
}
</style>
