<script setup>
import { Icon } from '@iconify/vue';
import { ref } from 'vue';

const cars = ref([
  {
    id: 1,
    title: "Honda Civic Walkaround",
    video: "/images/video-1.mp4.mp4",
    thumbnail: "/images/civic_new_banner_2021.png",
    description: "Detailed look at Honda Civic exterior and interior features.",
    duration: "4:32",
    views: "12.5K"
  },
  {
    id: 2,
    title: "Toyota Corolla Cross Walkaround",
    video: "/images/video-1.mp4.mp4",
    thumbnail: "/images/toyotacorollacross.jpeg",
    description: "Explore the Corolla Cross with modern design insights.",
    duration: "5:18",
    views: "9.8K"
  },
  {
    id: 3,
    title: "Nissan X-Trail Walkaround",
    video: "/images/video-1.mp4.mp4",
    thumbnail: "/images/nissan (2).png",
    description: "Full tour of the Nissan X-Trail SUV features and comfort.",
    duration: "6:45",
    views: "15.2K"
  },
]);

const featuredVideo = ref({
  title: "Toyota RAV4 Premium Edition",
  video: "/images/video-1.mp4.mp4",
  thumbnail: "/images/rav4-1.jpg",
  description: "In-depth look at the Toyota RAV4 — exterior, interior, and performance.",
  duration: "7:22",
  views: "24.7K"
});

const isPlaying = ref(false);
const activeVideo = ref(null);

const playVideo = (id) => {
  activeVideo.value = id;
  isPlaying.value = true;
};


const contactSales = () => {
  alert('Contact form would open here. In a real app, this would open a modal or navigate to a contact page.');
};
</script>

<template>
  <div class="bg-gradient-to-br from-slate-50 via-white to-slate-100">
    <div class="fixed inset-0 overflow-hidden pointer-events-none">
      <div class="absolute top-0 right-0 w-96 h-96 bg-red-500/10 rounded-full -translate-y-1/3 translate-x-1/3 blur-3xl animate-pulse-slow"></div>
      <div class="absolute bottom-0 left-0 w-[32rem] h-[32rem] bg-red-600/10 rounded-full translate-y-1/3 -translate-x-1/3 blur-3xl animate-pulse-slow delay-1000"></div>
      <div class="absolute top-1/2 left-1/4 w-64 h-64 bg-red-500/5 rounded-full blur-3xl animate-pulse-slow delay-500"></div>
      <div class="absolute inset-0 opacity-[0.03] bg-grid-pattern"></div>
    </div>

    <main class="relative z-10">
      <section class="relative h-[70vh] flex items-center justify-center bg-black text-white">
        <img
          :src="featuredVideo.thumbnail"
          alt="Car Walkaround"
          class="absolute inset-0 w-full h-full object-cover opacity-70"
        />
        <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent"></div>
        <div class="relative z-10 text-center px-6 max-w-3xl">
          <h1 class="text-4xl md:text-6xl font-bold mb-4">Live Walk Around</h1>
          <p class="mt-4 text-lg md:text-xl mb-8">
            Explore your favorite cars up close with our exclusive walkaround videos.
          </p>
          <button class="px-8 py-3 bg-gradient-to-r from-red-800 to-red-600 text-white font-semibold rounded-full shadow-lg hover:shadow-xl transition flex items-center justify-center mx-auto">
            <Icon icon="mdi:play" class="w-5 h-5 mr-2" />
            Watch Featured Video
          </button>
        </div>
      </section>
      <section class="max-w-6xl mx-auto px-4 py-16">
        <div class="flex justify-between items-center mb-8">
          <h2 class="text-3xl font-bold text-gray-800">Featured Walkaround</h2>
          <div class="flex items-center space-x-4">
            <span class="text-gray-600">{{ featuredVideo.views }} views</span>
            <span class="text-gray-600">•</span>
            <span class="text-gray-600">{{ featuredVideo.duration }}</span>
          </div>
        </div>
        
        <div class="relative w-full aspect-video rounded-2xl overflow-hidden shadow-xl bg-black">
          <video 
            class="w-full h-full object-cover" 
            controls 
            :poster="featuredVideo.thumbnail"
            @play="isPlaying = true"
            @pause="isPlaying = false"
          >
            <source :src="featuredVideo.video" type="video/mp4" />
            Your browser does not support the video tag.
          </video>
          
          <div v-if="!isPlaying" class="absolute inset-0 flex items-center justify-center">
            <div class="w-20 h-20 bg-white/90 rounded-full flex items-center justify-center cursor-pointer hover:bg-white transition" @click="playVideo('featured')">
              <Icon icon="mdi:play" class="w-10 h-10 text-red-800 ml-1" />
            </div>
          </div>
        </div>
        
        <div class="mt-6">
          <h3 class="text-2xl font-bold text-gray-800">{{ featuredVideo.title }}</h3>
          <p class="mt-2 text-gray-600">{{ featuredVideo.description }}</p>
        </div>
      </section>

      <section class="max-w-6xl mx-auto px-4 py-16">
        <div class="flex justify-between items-center mb-8">
          <h2 class="text-3xl font-bold text-gray-800">More Walkarounds</h2>
          <div class="flex space-x-4">
            <button class="px-4 py-2 bg-gray-100 hover:bg-gray-200 rounded-lg transition">Newest</button>
            <button class="px-4 py-2 bg-gray-100 hover:bg-gray-200 rounded-lg transition">Popular</button>
            <button class="px-4 py-2 bg-gray-100 hover:bg-gray-200 rounded-lg transition">SUVs</button>
          </div>
        </div>
        
        <div class="grid md:grid-cols-3 gap-8">
          <div
            v-for="car in cars"
            :key="car.id"
            class="bg-white rounded-xl shadow-md overflow-hidden hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1"
          >
            <div class="relative aspect-video">
              <img 
                :src="car.thumbnail" 
                :alt="car.title"
                class="w-full h-full object-cover"
              />
              <div class="absolute inset-0 bg-black/30 flex items-center justify-center opacity-0 hover:opacity-100 transition">
                <div class="w-16 h-16 bg-white/90 rounded-full flex items-center justify-center cursor-pointer" @click="playVideo(car.id)">
                  <Icon icon="mdi:play" class="w-8 h-8 text-red-800 ml-1" />
                </div>
              </div>
              <div class="absolute bottom-2 right-2 bg-black/70 text-white text-xs px-2 py-1 rounded">
                {{ car.duration }}
              </div>
            </div>
            <div class="p-5">
              <h3 class="text-lg font-bold text-gray-800">{{ car.title }}</h3>
              <p class="text-sm text-gray-600 mt-2">{{ car.description }}</p>
              <div class="flex justify-between items-center mt-4">
                <div class="flex items-center text-gray-500 text-sm">
                  <Icon icon="mdi:eye" class="w-4 h-4 mr-1" />
                  {{ car.views }} views
                </div>
                <button class="text-red-800 hover:text-red-600 text-sm font-medium">
                  Watch Now
                </button>
              </div>
            </div>
          </div>
        </div>
        
        <div class="mt-12 text-center">
          <button class="px-6 py-3 bg-gradient-to-r from-primary to-secondary text-white font-semibold rounded-lg shadow-lg hover:shadow-xl transition">
            Load More Videos
          </button>
        </div>
      </section>

      <section class="bg-gradient-to-r from-primary to-secondary py-16 text-center text-white">
        <div class="max-w-3xl mx-auto px-4">
          <h2 class="text-3xl md:text-4xl font-bold mb-4">Ready to Pre-Order Your Dream Car?</h2>
          <p class="mt-2 text-lg md:text-xl mb-8 max-w-2xl mx-auto">
            Contact us today and reserve your vehicle with exclusive pre-order benefits.
          </p>
          <div class="flex flex-col sm:flex-row justify-center gap-4">
            <button
              @click="contactSales"
              class="px-8 py-3 bg-white text-red-800 font-semibold rounded-full shadow-lg hover:shadow-xl transition flex items-center justify-center"
            >
              <Icon icon="mdi:phone" class="w-5 h-5 mr-2" />
              Contact Sales
            </button>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>