<script setup>
const activeMenu = ref(null);
const activeSubmenu = ref(null);
const searchQuery = ref("");
const menus = [
  {
    title: "About Us",
items: [
  { title: "Why Car Corporations", icon: "mdi:information-outline", to: "/about/whyCarCorporationsBD" },
  { title: "Message from Founder", icon: "mdi:account-tie", to: "/about/founder-message" },
  { title: "Message from Co-Founder", icon: "mdi:account-multiple", to: "/about/cofounder-message" },
  { title: "Message from CEO", icon: "mdi:account-tie-hat", to: "/showrooms" },
  { title: "Head Office", icon: "mdi:office-building-marker", to: "/head-office/head-office" },
  { title: "Bank Details", icon: "mdi:bank", to: "/testimonial/testimonial" },
],

  },
  {
    title: "Live Auction",
    items: [
      { title: "Buy from Live Auction", icon: "mdi:flash", to: "/buyFromAuction" },
      {
        title: "How to Pre order", icon: "mdi:book-open-page-variant", to: "/Pre-order/how-to-pre-order",
        children: [
          { title: "Pre Order Now", icon: "mdi:clock-fast", to: "/Pre-order/pre-order" }
        ]
      },
      { title: "Auction Sheet Guide", icon: "mdi:file-document-outline", to: "/auctionSheet" },
      { title: "Terms and Conditions", icon: "mdi:book-open-page-variant", to: "/termCondition" },
    ]
  },
  {
    title: "Services",
    items: [
      { title: "Live Auction", icon: "mdi:audio-video", to: "/carAuction" },
      { title: "Vehicle Import", icon: "mdi:car-hatchback", to: "/vehicleImport" },
      { title: "Reconditioned Vehicles", icon: "mdi:car-wash", to: "/reconditionedVehicles" },
      { title: "Car Dealer Services", icon: "mdi:handshake", to: "/carDealerService" },
    ],
  }
];
</script>

<template>
  <header class="sticky top-0 z-40 bg-white/95 backdrop-blur-md border-b border-gray-100 shadow-sm">
    <div class="container mx-auto">
      <div class="flex items-center justify-between h-20">
        <NuxtLink to="/" class="flex items-center group relative">
          <img src="/images/logo.jpg" alt="CarCorporation BD" class="h-auto w-12 rounded-full" />
        </NuxtLink>
        <nav class="hidden lg:flex items-center space-x-1">
          <div class="relative">
            <NuxtLink to="/"
              class="px-5 py-2 text-gray-800 font-medium hover:text-primary transition flex items-center group relative">
              <span class="relative z-10">Home</span>
              <span
                class="absolute bottom-0 left-1/2 w-0 h-0.5 bg-primary transform -translate-x-1/2 transition-all duration-300 group-hover:w-4/5"></span>
            </NuxtLink>
          </div>
          <div class="relative">
            <NuxtLink to="/StockList"
              class="px-5 py-2 text-gray-800 font-medium hover:text-primary transition flex items-center group relative">
              <span class="relative z-10">Stock List</span>
              <span
                class="absolute bottom-0 left-1/2 w-0 h-0.5 bg-primary transform -translate-x-1/2 transition-all duration-300 group-hover:w-4/5"></span>
            </NuxtLink>
          </div>

          <div v-for="(menu, index) in menus" :key="index" @mouseenter="activeMenu = index"
            @mouseleave="activeMenu = null; activeSubmenu = null" class="relative">
            <button
              class="px-5 py-2 text-gray-800 font-medium hover:text-primary transition flex items-center group relative">
              <span class="relative z-10" :class="menu.title === 'Live Auction' ? 'neon-text' : ''">
                {{ menu.title }}
              </span>

              <span
                class="absolute bottom-0 left-1/2 w-0 h-0.5 bg-primary transform -translate-x-1/2 transition-all duration-300 group-hover:w-4/5"></span>
              <Icon name="mdi:chevron-down"
                class="ml-1.5 text-gray-400 text-lg transition-transform duration-200 group-hover:rotate-180 group-hover:text-primary" />
            </button>

            <transition name="dropdown">
              <div v-if="activeMenu === index"
                class="absolute left-1/2 transform -translate-x-1/2 mt-3 w-64 bg-white rounded-xl shadow-2xl border border-gray-100">
                <div class="py-2">
                  <div v-for="(item, i) in menu.items" :key="i" class="relative group"
                    @mouseenter="item.children && (activeSubmenu = i)"
                    @mouseleave="item.children && (activeSubmenu = null)">

                    <NuxtLink :to="item.to"
                      class="px-5 py-3 flex items-center text-gray-700 hover:bg-gray-50 hover:text-primary transition-all duration-200 group">
                      <Icon :name="item.icon"
                        class="mr-3 text-primary text-lg group-hover:scale-110 transition-transform" />
                      <span class="font-medium">{{ item.title }}</span>
                      <Icon v-if="item.children" name="mdi:chevron-right"
                        class="ml-auto text-gray-300 group-hover:text-primary transition-colors" />
                    </NuxtLink>

                    <transition name="dropdown">
                      <div v-if="item.children && activeSubmenu === i"
                        class="absolute left-full top-0 ml-1 w-auto min-w-[14rem] bg-white rounded-xl shadow-2xl z-50 overflow-hidden border border-gray-100">
                        <div class="py-2">
                          <NuxtLink v-for="(child, childIndex) in item.children" :key="childIndex" :to="child.to"
                            class="px-5 py-3 flex items-center text-gray-700 hover:bg-gray-50 hover:text-primary transition-all duration-200 group">
                            <Icon :name="child.icon"
                              class="mr-3 text-primary text-lg group-hover:scale-110 transition-transform" />
                            <span class="font-medium">{{ child.title }}</span>
                          </NuxtLink>
                        </div>
                      </div>
                    </transition>
                  </div>
                </div>
              </div>
            </transition>
          </div>

          <div class="relative">
            <NuxtLink to="/contact-us/contact"
              class="px-5 py-2 text-gray-800 font-medium hover:text-primary transition flex items-center group relative">
              <span class="relative z-10">Contact Us</span>
            </NuxtLink>
          </div>
        </nav>

        <div class="flex items-center space-x-4">
          <div class="relative hidden md:block">
            <div class="relative group">
              <input v-model="searchQuery" type="text" placeholder="Find cars, parts & more..."
                class="pl-12 pr-5 py-3 border-0 bg-gray-50 rounded-full focus:ring-2 focus:ring-primary/50 focus:bg-white w-56 transition-all duration-300 group-hover:w-64 focus:w-64 shadow-inner" />
              <div class="absolute inset-y-0 left-0 flex items-center pl-4 pointer-events-none">
                <Icon name="mdi:magnify" class="text-xl text-gray-500 group-hover:text-primary transition-colors" />
              </div>
              <button v-if="searchQuery" @click="searchQuery = ''"
                class="absolute right-3 top-1/2 transform -translate-y-1/2 text-gray-400 hover:text-primary transition-colors">
                <Icon name="mdi:close" class="text-lg" />
              </button>
            </div>
          </div>
          <NuxtLink to="/login"
            class="hidden xl:flex items-center px-4 py-2 bg-gradient-to-r from-primary to-secondary text-white font-medium rounded-full shadow-lg hover:shadow-xl transition-all hover:scale-[1.02] group">
            <Icon name="material-symbols:account-circle"
              class="mr-2 text-lg group-hover:scale-110 transition-transform" />
            <span>Login</span>
          </NuxtLink>
          <button class="lg:hidden p-2 rounded-full bg-gray-50 hover:bg-gray-100 transition-colors">
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

.neon-text {
  color: #ff1a1a;
  text-shadow:
    0 0 5px #ff1a1a,
    0 0 10px #ff1a1a,
    0 0 20px #ff1a1a,
    0 0 40px #8b0000,
    0 0 80px #8b0000;
  animation: neonPulse 1.5s ease-in-out infinite alternate;
}

@keyframes neonPulse {
  from {
    text-shadow:
      0 0 2px #ff1a1a;
    color: #8b0000;
  }

  to {
    text-shadow:
      0 0 2px #ff1a1a;
    color: black;
  }
}
</style>