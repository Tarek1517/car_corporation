<script setup>
const brands = [
  { name: "honda", logo: "/images/honda.png" },
  { name: "Toyota", logo: "/images/Toyota.png" },
  { name: "Suzuki", logo: "/images/suzuki.png" },
  { name: "Nissan", logo: "/images/Nissan.png" },
  { name: "Volkswagen", logo: "/images/Volkswagen.png" },
  { name: "Mahindra", logo: "/images/Mahindra.png" },
  { name: "Hyundai", logo: "/images/Hyundai.png" },
];
</script>

<template>
  <div class="w-full py-16 bg-gradient-to-b from-gray-50 via-white to-gray-100">
    <!-- Section Header -->
    <div class="text-center mb-10">
      <div
        class="inline-flex items-center px-4 py-2 bg-gradient-to-r from-primary to-secondary text-white rounded-full text-sm font-semibold mb-4 shadow-lg"
      >
        <Icon name="heroicons:sparkles" class="w-4 h-4 mr-2 animate-pulse" />
        Premium Brands
      </div>

      <h2 class="text-4xl md:text-5xl font-extrabold text-gray-900 mb-4">
        Explore Our
        <span
          class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary"
          >Brand</span
        >
        Collection
      </h2>
      <p class="text-lg md:text-xl text-gray-600 max-w-4xl mx-auto">
        Discover top-quality brands offering exceptional products and innovative
        designs for every lifestyle.
      </p>
    </div>

    <!-- Brand Carousel -->
    <div class="container mx-auto px-10">
      <UCarousel
        :items="brands"
        loop
        auto-scroll
        :slides-per-view="6"
        :slide-to-scroll="1"
        class="overflow-visible"
        :ui="{ item: 'basis-1/6 p-3' }"
      >
        <template #default="{ item: brand }">
          <div
            class="relative group bg-gradient-to-r from-primary/15 to-secondary/10 rounded-3xl flex flex-col items-center justify-center p-6 transition-all duration-500 hover:scale-105 cursor-pointer border border-gray-100"
          >
            <!-- Brand Logo with Animated Gradient Border -->
            <div
              class="w-24 h-24 md:w-28 md:h-28 rounded-full flex items-center justify-center overflow-hidden mb-4 relative group-hover:scale-110 transition-transform duration-500"
            >
              <!-- Animated gradient border -->
              <div
                class="absolute inset-0 rounded-full bg-gradient-to-r from-primary to-secondary p-1 animate-spin-slow"
              >
                <div class="absolute inset-0.5 rounded-full bg-white"></div>
              </div>

              <!-- Logo container -->
              <div
                class="relative w-full h-full rounded-full bg-white flex items-center justify-center p-3 z-10"
              >
                <NuxtImg
                  :src="brand.logo"
                  :alt="brand.name"
                  class="w-full h-full object-contain transition-transform duration-500 group-hover:scale-110"
                  loading="lazy"
                  format="webp"
                  quality="90"
                />
              </div>
            </div>

            <!-- Hidden brand name that slides up on hover -->
            <div
              class="overflow-hidden h-0 group-hover:h-6 transition-all duration-500"
            >
              <span
                class="text-sm font-semibold text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary transform translate-y-4 group-hover:translate-y-0 transition-transform duration-500"
              >
                {{ brand.name }}
              </span>
            </div>
          </div>
        </template>
      </UCarousel>
    </div>
  </div>
</template>

<style scoped>
.animate-spin-slow {
  animation: spin 8s linear infinite;
}

.animate-shine {
  animation: shine 2s linear infinite;
}

@keyframes spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

@keyframes shine {
  0% {
    transform: translateX(-100%) rotate(45deg);
  }
  100% {
    transform: translateX(200%) rotate(45deg);
  }
}
</style>
