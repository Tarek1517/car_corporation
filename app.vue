<template>
  <div>
    <NuxtRouteAnnouncer />
    <NuxtLayout>
      <NuxtPage />
      <!-- Custom Car Scrollbar with Headlight Effect -->
      <div class="fixed right-4 bottom-4 z-50 hidden md:block">
        <div class="relative w-16 h-16 group cursor-pointer" @click="scrollToTop">
          <!-- Main Car Image (Visible by default) -->
          <img
            src="/images/car.png"
            alt="Scroll car"
            class="w-full h-full object-contain transform transition-all duration-500 absolute inset-0"
          />
          
          <!-- Hover Car Image with Headlights On -->
          <img
            src="/images/car-focus.png"
            alt="Scroll car with headlights on"
            class="w-full h-full object-contain transform transition-all duration-500 opacity-0 group-hover:opacity-100 group-hover:scale-105 absolute inset-0"
          />
        </div>
      </div>
    </NuxtLayout>
  </div>
</template>

<script setup>
const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' });
};
</script>

<style>
@import "tailwindcss";
@import "@nuxt/ui";
@theme {
  --color-primary: #8b0000;
  --color-secondary: #ff0000;
}

/* Hide browser scrollbar completely */
::-webkit-scrollbar {
  display: none;
}

/* Hide scrollbar for Firefox */
* {
  scrollbar-width: none;
}

/* Hide scrollbar for IE and Edge */
body {
  -ms-overflow-style: none;
}

/* Background pattern with subtle car elements */
body {
  position: relative;
}

body::before {
  content: "";
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: 
    radial-gradient(circle at 20% 30%, rgba(139, 0, 0, 0.03) 1px, transparent 1px),
    radial-gradient(circle at 80% 70%, rgba(255, 0, 0, 0.03) 1px, transparent 1px);
  background-size: 50px 50px;
  pointer-events: none;
  z-index: -1;
}
</style>