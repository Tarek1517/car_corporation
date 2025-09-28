<script setup>
const mobileMenuOpen = ref(false);
const currencyDropdownOpen = ref(false);
const currentCurrency = ref("BDT");
const currencies = ["BDT", "USD", "EUR", "GBP"];
const activeMenu = ref(null);
const activeSubmenu = ref(null);

const menus = [
  {
    title: "About Us",
    items: [
      { title: "Why Car Corporations", icon: "mdi:information-outline", to: "/about/whyCarCorporationsBD" },
      { title: "Message from Founder", icon: "mdi:account-tie", to: "/message/message-founder" },
      { title: "Message from Co-Founder", icon: "mdi:account-multiple", to: "/message/message-co-founder" },
      { title: "Message from CEO", icon: "mdi:account-tie-hat", to: "/message/message-ceo" },
      { title: "Head Office", icon: "mdi:office-building-marker", to: "/head-office/head-office" },
      { title: "Bank Details", icon: "mdi:bank", to: "/about/Bank-details" },
      {
        title: "Gallery of Happiness", icon: "mdi:image", to: "/",
        children: [
          { title: "Picture Gallery", icon: "mdi:image-multiple", to: "/about/Gallery-Happiness" },
          { title: "Client Speaks for US", icon: "mdi:account-group", to: "/about/client" }
        ]
      },
      {
        title: "News Room", icon: "mdi:newspaper", to: "/",
        children: [
          { title: "Blogs", icon: "mdi:newspaper-variant", to: "/blogs/blogPost" },
          { title: "FAQs", icon: "mdi:help-circle", to: "/about/FAQs" }
        ]
      }
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
    title: "Stock",
    items: [
      { title: "Find a car", icon: "mdi:information-outline", to: "/Ready-Stock/FindACar" },
      { title: "Walk-Around", icon: "mdi:account-tie", to: "/Ready-Stock/Walk-around" },
      { title: "Video Reviews", icon: "mdi:account-multiple", to: "/Ready-Stock/review" },
      { title: "Showroom", icon: "mdi:account-tie-hat", to: "/showrooms" },
      { title: "Stock List", icon: "mdi:car", to: "/StockList" }
    ]
  },
];

const toggleMenu = (index) => {
  if (activeMenu.value === index) {
    activeMenu.value = null;
    activeSubmenu.value = null;
  } else {
    activeMenu.value = index;
    activeSubmenu.value = null;
  }
};

const toggleSubmenu = (index) => {
  if (activeSubmenu.value === index) {
    activeSubmenu.value = null;
  } else {
    activeSubmenu.value = index;
  }
};
</script>

<template>
  <div class="lg:hidden sticky top-0 z-50 bg-white shadow-md">
    <div class="bg-gray-900 text-gray-100 text-sm py-3 px-4 flex items-center justify-between">
      <div class="flex items-center">
        <img src="/images/logo.jpg" alt="CarCorporation BD" class="h-8 w-8 rounded-full" />
      </div>
      <button @click="mobileMenuOpen = !mobileMenuOpen" class="p-2 rounded-md hover:bg-gray-800 transition-colors">
        <Icon :name="mobileMenuOpen ? 'mdi:close' : 'mdi:menu'" class="text-xl" />
      </button>
    </div>
    <transition name="slide">
      <div v-if="mobileMenuOpen" class="bg-white shadow-lg">
        <div class="p-4 border-b border-gray-200">
          <div class="flex items-center gap-2 mb-3">
            <Icon name="ph:phone-light" class="text-lg text-primary" />
            <span>Hotline: <span class="font-medium">09613 787878</span></span>
          </div>
          <div class="flex items-center gap-2 mb-3">
            <Icon name="mdi:map-marker-outline" class="text-lg text-primary" />
            <span>Showroom: <span class="font-medium">Gulshan-1, Dhaka</span></span>
          </div>
          <div class="flex items-center gap-2 mb-3">
            <Icon name="mdi:clock-outline" class="text-lg text-primary" />
            <span>Working Hours: <span class="font-medium">9AM - 11PM</span></span>
          </div>
          <div class="flex items-center space-x-4 mt-4">
            <a href="#" class="text-primary hover:text-blue-400 transition-colors">
              <Icon name="mdi:facebook" class="text-lg" />
            </a>
            <a href="#" class="text-primary hover:text-pink-400 transition-colors">
              <Icon name="mdi:instagram" class="text-lg" />
            </a>
            <a href="#" class="text-primary hover:text-blue-400 transition-colors">
              <Icon name="mdi:twitter" class="text-lg" />
            </a>
            <a href="#" class="text-primary hover:text-red-400 transition-colors">
              <Icon name="mdi:youtube" class="text-lg" />
            </a>
          </div>
          <div class="mt-4">
            <div class="flex items-center justify-between">
              <span class="font-medium">Currency</span>
              <button @click="currencyDropdownOpen = !currencyDropdownOpen" class="flex items-center gap-1">
                <span>{{ currentCurrency }}</span>
                <Icon name="mdi:chevron-down" class="text-lg transition-transform" :class="{ 'rotate-180': currencyDropdownOpen }" />
              </button>
            </div>
            <div v-if="currencyDropdownOpen" class="mt-2 bg-gray-50 rounded-md">
              <button v-for="currency in currencies" :key="currency" @click="currentCurrency = currency; currencyDropdownOpen = false" class="block w-full text-left px-4 py-2 text-sm hover:bg-gray-100">
                {{ currency }}
              </button>
            </div>
          </div>
        </div>
        <nav class="p-4">
          <NuxtLink to="/" class="block py-3 font-medium text-gray-800 hover:text-primary" @click="mobileMenuOpen = false">Home</NuxtLink>

          <div v-for="(menu, index) in menus" :key="index">
            <button @click="toggleMenu(index)" class="w-full flex items-center justify-between py-3 font-medium text-gray-800 hover:text-primary">
              <span>{{ menu.title }}</span>
              <Icon name="mdi:chevron-down" class="text-lg transition-transform" :class="{ 'rotate-180': activeMenu === index }" />
            </button>
            <div v-if="activeMenu === index" class="pl-4 bg-gray-50 rounded-md mt-1">
              <div v-for="(item, i) in menu.items" :key="i">
                <div v-if="!item.children">
                  <NuxtLink :to="item.to" class="block py-2 text-gray-600 hover:text-primary" @click="mobileMenuOpen = false">
                    {{ item.title }}
                  </NuxtLink>
                </div>
                <div v-else>
                  <button @click="toggleSubmenu(i)" class="w-full flex items-center justify-between py-2 text-gray-600 hover:text-primary">
                    <span>{{ item.title }}</span>
                    <Icon name="mdi:chevron-down" class="text-lg transition-transform" :class="{ 'rotate-180': activeSubmenu === i }" />
                  </button>
                  <div v-if="activeSubmenu === i" class="pl-4 bg-white rounded-md mt-1">
                    <NuxtLink v-for="(child, childIndex) in item.children" :key="childIndex" :to="child.to" class="block py-2 text-gray-600 hover:text-primary" @click="mobileMenuOpen = false">
                      {{ child.title }}
                    </NuxtLink>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <NuxtLink to="/verifyAuction" class="block py-3 font-medium text-gray-800 hover:text-primary" @click="mobileMenuOpen = false">True Report</NuxtLink>
          <NuxtLink to="/cars/dutyCalculator" class="block py-3 font-medium text-gray-800 hover:text-primary" @click="mobileMenuOpen = false">Duty Calculator</NuxtLink>
          <NuxtLink to="/shipping-info" class="block py-3 font-medium text-gray-800 hover:text-primary" @click="mobileMenuOpen = false">Shipping</NuxtLink>

          <div>
            <button @click="toggleMenu('contact')" class="w-full flex items-center justify-between py-3 font-medium text-gray-800 hover:text-primary">
              <span>Contact</span>
              <Icon name="mdi:chevron-down" class="text-lg transition-transform" :class="{ 'rotate-180': activeMenu === 'contact' }" />
            </button>
            <div v-if="activeMenu === 'contact'" class="pl-4 bg-gray-50 rounded-md mt-1">
              <NuxtLink to="/contact-us/Dhaka-Office" class="block py-2 text-gray-600 hover:text-primary" @click="mobileMenuOpen = false">Dhaka Office</NuxtLink>
              <NuxtLink to="/contact-us/Chittagong-Office" class="block py-2 text-gray-600 hover:text-primary" @click="mobileMenuOpen = false">Chittagong Office</NuxtLink>
            </div>
          </div>
        </nav>
      </div>
    </transition>
  </div>
</template>

<style scoped>
.slide-enter-active,
.slide-leave-active {
  transition: all 0.3s ease;
}
.slide-enter-from,
.slide-leave-to {
  opacity: 0;
  transform: translateY(-20px);
}
</style>