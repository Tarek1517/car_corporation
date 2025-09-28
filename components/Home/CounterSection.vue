<script setup>
const showVideo = ref(false);

const counters = [
  { title: "Live Auction Access", value: "120K" },
  { title: "Vehicle Import", value: "2K" },
  { title: "Reconditioned Vehicles", value: "10K" },
  { title: "Car Dealer Services", value: "40" },
];
</script>

<template>
  <div class="w-full py-16 bg-gradient-to-b from-gray-50 via-white to-gray-100">
    <!-- 1st Section -->
    <section
      class="relative min-h-[650px] flex items-center justify-center bg-cover bg-fixed bg-center text-white overflow-hidden"
      style="background-image: url('/images/counter.jpg')"
    >
      <!-- Enhanced overlay with gradient -->
      <div
        class="absolute inset-0 bg-gradient-to-r from-primary/35 to-primary/20"
      ></div>

      <!-- Animated floating elements -->
      <div
        class="absolute top-20 left-10 w-6 h-6 rounded-full bg-white/20 animate-float"
      ></div>
      <div
        class="absolute top-40 right-20 w-8 h-8 rounded-full bg-primary/30 animate-float animation-delay-1000"
      ></div>
      <div
        class="absolute bottom-32 left-24 w-5 h-5 rounded-full bg-secondary/30 animate-float animation-delay-2000"
      ></div>

      <!-- Video Modal (unchanged structure) -->
      <UModal v-model="showVideo" size="4xl" title="Watch Video">
        <div
          class="container mx-auto px-6 relative z-10 flex flex-col items-center justify-center text-center"
        >
          <div
            class="flex flex-col items-center justify-center max-w-7xl mx-auto text-center"
          >
            <UButton
              @click="showVideo = true"
              class="group relative w-24 h-24 rounded-full bg-white/20 backdrop-blur-md border-2 border-white/30 flex items-center justify-center shadow-2xl hover:shadow-3xl transition-all duration-500 hover:scale-110"
            >
              <div
                class="absolute inset-0 rounded-full bg-white/20 animate-ping group-hover:animate-none"
              ></div>
              <div
                class="absolute inset-2 rounded-full bg-gradient-to-r from-primary to-secondary"
              ></div>
              <Icon
                name="heroicons:play-20-solid"
                class="w-10 h-10 text-white relative z-10 ml-1 transition-transform group-hover:scale-110"
              />
            </UButton>

            <!-- Main heading with gradient -->
            <h2
              class="text-5xl md:text-6xl lg:text-7xl font-bold text-white mb-6 leading-tight"
            >
              Discover
              <span
                class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary"
                >Exclusive </span
              >
              Vehicle Solutions
            </h2>
          </div>
        </div>
        <template #body>
          <div class="aspect-video w-full">
            <!-- Only load iframe when modal is open -->
            <iframe
              v-if="showVideo"
              class="w-full h-full rounded-lg"
              src="https://www.youtube.com/embed/dQw4w9WgXcQ?autoplay=1"
              title="YouTube video"
              frameborder="0"
              allow="autoplay; encrypted-media"
              allowfullscreen
            ></iframe>
          </div>
        </template>
      </UModal>
    </section>

    <!-- 2nd Section -->
    <section class="relative -mt-40 overflow-hidden px-6">
      <div
        class="container bg-gradient-to-r from-primary via-primary/90 to-secondary mx-auto px-8 py-12 rounded-3xl shadow-2xl relative z-10 border border-white/20"
      >
        <div
          class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8 text-center"
        >
          <div
            v-for="(counter, index) in counters"
            :key="index"
            class="p-8 bg-gradient-to-r from-primary to-secondary rounded-2xl shadow-lg hover:scale-105 transform transition-all duration-300 border border-white/10 group"
          >
            <!-- Animated counter number -->
            <h3 class="text-5xl md:text-6xl font-bold text-white mb-4">
              {{ counter.value }}+
            </h3>

            <!-- Title with hover effect -->
            <p
              class="text-lg font-semibold text-gray-100 tracking-wide uppercase group-hover:text-white transition-colors"
            >
              {{ counter.title }}
            </p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>
