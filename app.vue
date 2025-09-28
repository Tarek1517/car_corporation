<template>
  <div>
    <NuxtRouteAnnouncer />
    <NuxtLayout>
      <NuxtPage />
      <div class="fixed right-4 bottom-4 z-50 hidden md:block">
        <div class="relative w-16 h-16 group cursor-pointer" @click="scrollToTop">
          <img
            src="/images/car.png"
            alt="Scroll car"
            class="w-full h-full object-contain transform transition-all duration-500 absolute inset-0"
          />
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
import { onMounted } from 'vue';

const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' });
};

onMounted(() => {
  const TAWK_PROPERTY_ID = '68ce5aed1ee8fa1927a91f1a';
  const TAWK_WIDGET_ID = '1j5j16cvt';

  const script = document.createElement('script');
  script.src = `https://embed.tawk.to/${TAWK_PROPERTY_ID}/${TAWK_WIDGET_ID}`;
  script.async = true;
  script.charset = 'UTF-8';
  script.setAttribute('crossorigin', '*');
  document.body.appendChild(script); 
});
</script>

<style>
@import "tailwindcss";
@import "@nuxt/ui";
@theme {
  --color-primary: #8b0000;
  --color-secondary: #ff0000;
}

::-webkit-scrollbar {
  display: none;
}

* {
  scrollbar-width: none;
}

body {
  -ms-overflow-style: none;
}

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