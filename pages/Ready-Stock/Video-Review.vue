<script setup>
import { ref } from 'vue';
import { Icon } from '@iconify/vue';

const videos = [
  {
    id: 'video-1',
    title: 'Main Video: BMW X5 Review',
    thumbnail: 'https://picsum.photos/seed/bmw-x5/600/338.jpg',
    duration: '15:30',
    views: '12,345',
    description: 'In-depth BMW X5 review and driving experience.'
  },
  {
    id: 'video-2',
    title: 'Toyota Corolla Cross Review',
    thumbnail: 'https://picsum.photos/seed/toyota-corolla/300/169.jpg',
    duration: '12:45',
    views: '8,923'
  },
  {
    id: 'video-3',
    title: 'Hyundai Tucson vs Honda CR-V Comparison',
    thumbnail: 'https://picsum.photos/seed/hyundai-tucson/300/169.jpg',
    duration: '18:22',
    views: '15,671'
  },
  {
    id: 'video-4',
    title: '2024 Mazda CX-5 First Drive',
    thumbnail: 'https://picsum.photos/seed/mazda-cx5/300/169.jpg',
    duration: '14:18',
    views: '9,845'
  }
];

const selectedVideo = ref(videos[0]);

const relatedVideos = computed(() => videos.filter(v => v.id !== selectedVideo.value.id));

function selectVideo(video) {
  selectedVideo.value = video;
}
</script>

<template>
<section class="w-full relative overflow-hidden bg-gradient-to-br from-slate-50 via-white to-slate-100">
        <div class="relative h-[500px] md:h-[600px] w-full">
      <img src="/images/review.jpg" alt="Showrooms Background"
        class="w-full h-full object-cover" />
      <div class="absolute inset-0 bg-black/50"></div>
      <div class="absolute inset-0 flex flex-col items-center justify-center text-center px-4 z-10">
        <h2 class="text-4xl md:text-5xl font-bold text-white drop-shadow-lg mb-4">
          Video
          <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary drop-shadow">
            Reviews
          </span>
        </h2>
        <p class="text-lg md:text-xl text-gray-200 max-w-2xl">
          Explore our state-of-the-art showrooms across Bangladesh — where
          innovation meets elegance and every detail is crafted for an exceptional experience.
        </p>
      </div>
    </div>
  <div class="relative z-10 px-4 md:px-12 py-6">
    <!-- Main Video -->
    <div class="relative rounded-2xl overflow-hidden shadow-lg mb-10">
      <img :src="selectedVideo.thumbnail" alt="Main video" class="w-full h-[400px] md:h-[500px] object-cover" />
      <div class="absolute inset-0 bg-black/40 flex flex-col justify-center items-center text-white px-4">
        <h2 class="text-3xl md:text-5xl font-bold text-center">{{ selectedVideo.title }}</h2>
        <p v-if="selectedVideo.description" class="mt-3 text-lg md:text-xl text-center">{{ selectedVideo.description }}</p>
      </div>
    </div>

    <!-- Related Videos -->
    <div class="bg-white rounded-3xl shadow-xl p-6">
      <h2 class="text-2xl font-bold text-gray-800 mb-6">Related Videos</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        <div v-for="video in relatedVideos" :key="video.id" 
             class="bg-gray-50 rounded-xl overflow-hidden transform transition-all hover:scale-105 hover:shadow-2xl hover:brightness-105 cursor-pointer group"
             @click="selectVideo(video)">
          <div class="relative">
            <img :src="video.thumbnail" alt="Video thumbnail" class="w-full h-48 md:h-40 object-cover group-hover:scale-110 transition-transform duration-500" />
            <div class="absolute inset-0 bg-gradient-to-t from-black/50 via-transparent to-transparent opacity-70"></div>
            <div class="absolute bottom-2 right-2 bg-black/70 text-white text-xs px-2 py-1 rounded">{{ video.duration }}</div>
            <div class="absolute inset-0 flex items-center justify-center opacity-0 group-hover:opacity-100 transition-opacity duration-300">
              <div class="w-12 h-12 bg-white/80 rounded-full flex items-center justify-center">
                <Icon icon="mdi:play" class="w-6 h-6 text-primary"/>
              </div>
            </div>
          </div>
          <div class="p-4">
            <h3 class="font-semibold text-gray-800 text-sm md:text-base line-clamp-2">{{ video.title }}</h3>
            <p class="text-gray-500 text-xs md:text-sm mt-1">{{ video.views }} views</p>
          </div>
        </div>
      </div>
    </div>

  </div>
</section>
</template>
