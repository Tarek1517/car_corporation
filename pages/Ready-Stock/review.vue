<script setup>
import { ref, onMounted } from 'vue'
import { useRoute } from 'vue-router'
import { useHead } from '@unhead/vue'

const route = useRoute()
const videoId = ref(route.params.id || 'sample-video-1')


const videoData = {
  title: 'Honda Civic 2024 Review',
  description: 'Comprehensive review of the new Honda Civic 2024 model, featuring performance, design, and features analysis.',
  duration: '15:32',
  views: '12,345',
  likes: '1,234',
  dislikes: '23',
  published: '2 days ago',
  channel: {
    name: 'Car Corporation',
    subscribers: '45.2K',
    avatar: '/images/avatar1.png'
  }
}

// Related videos
const relatedVideos = [
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
]

const comments = [
  {
    id: 'comment-1',
    user: {
      name: 'Rahim Khan',
      avatar: 'https://picsum.photos/seed/rahim-khan/40/40.jpg'
    },
    text: 'Great review! The interior design looks amazing. Can you do a follow-up video on the fuel efficiency?',
    likes: 24,
    replies: 3,
    time: '1 day ago'
  },
  {
    id: 'comment-2',
    user: {
      name: 'Sara Ahmed',
      avatar: 'https://picsum.photos/seed/sara-ahmed/40/40.jpg'
    },
    text: 'Very informative! I was considering buying this model and your review helped me make my decision.',
    likes: 18,
    replies: 1,
    time: '2 days ago'
  },
  {
    id: 'comment-3',
    user: {
      name: 'Ali Hassan',
      avatar: 'https://picsum.photos/seed/ali-hassan/40/40.jpg'
    },
    text: 'The acceleration test was impressive! How does it compare to the previous model?',
    likes: 12,
    replies: 5,
    time: '3 days ago'
  }
]

onMounted(() => {
  useHead({
    title: `${videoData.title} - Car Corporation`,
    meta: [
      { name: 'description', content: videoData.description },
      { property: 'og:title', content: `${videoData.title} - Car Corporation` },
      { property: 'og:description', content: videoData.description },
      { property: 'og:image', content: `https://picsum.photos/seed/video-thumbnail-${videoId.value}/1200/630.jpg` }
    ]
  })
})
</script>

<template>
  <div class="min-h-screen bg-gradient-to-br from-slate-50 via-white to-slate-100">
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
    <div class="container mx-auto px-4 py-8 relative z-10">
    <div class="relative rounded-2xl overflow-hidden shadow-lg mb-10">
      <img :src="`/images/video-thumbnails/${videoId.value}.jpg`" alt="Main video" class="w-full h-[400px] md:h-[500px] object-cover" />
      <div class="absolute inset-0 bg-black/40 flex flex-col justify-center items-center text-white px-4">
        <h2 class="text-3xl md:text-5xl font-bold text-center">{{ videoData.title }}</h2>
        <p v-if="videoData.description" class="mt-3 text-lg md:text-xl text-center">{{ videoData.description }}</p>
      </div>
    </div>

      <!-- Video info -->
      <div class="bg-white rounded-2xl shadow-lg p-6 mb-8">
        <h1 class="text-2xl font-bold text-gray-800 mb-2">{{ videoData.title }}</h1>
        <p class="text-gray-600 mb-4">{{ videoData.description }}</p>
        
        <div class="flex items-center justify-between mb-4">
          <div class="flex items-center space-x-4">
            <img
              :src="`/images/avatars/channel-avatar.jpg`"
              alt="Channel avatar"
              class="w-10 h-10 rounded-full"
            />
            <div>
              <p class="font-medium text-gray-800">{{ videoData.channel.name }}</p>
              <p class="text-sm text-gray-500">{{ videoData.channel.subscribers }} subscribers</p>
            </div>
          </div>
          
          <div class="flex items-center space-x-6">
            <div class="flex items-center space-x-2">
              <span class="text-gray-600">{{ videoData.views }} views</span>
            </div>
            <div class="flex items-center space-x-2">
              <span class="text-gray-600">{{ videoData.duration }}</span>
            </div>
          </div>
        </div>
        
        <div class="flex space-x-4">
          <button class="flex items-center space-x-2 bg-primary text-white px-4 py-2 rounded-full hover:bg-primary/90 transition">
            <i class="fas fa-thumbs-up"></i>
            <span>Like ({{ videoData.likes }})</span>
          </button>
          <button class="flex items-center space-x-2 bg-gray-100 text-gray-700 px-4 py-2 rounded-full hover:bg-gray-200 transition">
            <i class="fas fa-thumbs-down"></i>
            <span>Dislike ({{ videoData.dislikes }})</span>
          </button>
          <button class="flex items-center space-x-2 bg-gray-100 text-gray-700 px-4 py-2 rounded-full hover:bg-gray-200 transition">
            <i class="fas fa-share"></i>
            <span>Share</span>
          </button>
          <button class="flex items-center space-x-2 bg-gray-100 text-gray-700 px-4 py-2 rounded-full hover:bg-gray-200 transition">
            <i class="fas fa-download"></i>
            <span>Download</span>
          </button>
        </div>
      </div>

      <!-- Comments section -->
      <div class="bg-white rounded-2xl shadow-lg p-6 mb-8">
        <h2 class="text-xl font-bold text-gray-800 mb-4">Comments ({{ comments.length }})</h2>
        
        <div class="space-y-4">
          <div v-for="comment in comments" :key="comment.id" class="border-b border-gray-100 pb-4 last:border-b-0">
            <div class="flex space-x-3">
              <img
                :src="`/images/avatars/${comment.user.name.toLowerCase().replace(' ', '-')}.jpg`"
                alt="User avatar"
                class="w-10 h-10 rounded-full"
              />
              <div class="flex-1">
                <div class="flex items-center justify-between">
                  <h3 class="font-medium text-gray-800">{{ comment.user.name }}</h3>
                  <span class="text-sm text-gray-500">{{ comment.time }}</span>
                </div>
                <p class="text-gray-700 mt-1">{{ comment.text }}</p>
                <div class="flex items-center space-x-4 mt-2">
                  <button class="flex items-center space-x-1 text-gray-500 hover:text-gray-700">
                    <i class="far fa-thumbs-up"></i>
                    <span class="text-sm">{{ comment.likes }}</span>
                  </button>
                  <button class="flex items-center space-x-1 text-gray-500 hover:text-gray-700">
                    <i class="far fa-flag"></i>
                    <span class="text-sm">Report</span>
                  </button>
                  <button class="flex items-center space-x-1 text-gray-500 hover:text-gray-700">
                    <i class="far fa-reply"></i>
                    <span class="text-sm">Reply</span>
                  </button>
                </div>
              </div>
            </div>
          </div>
        </div>
        
        <div class="mt-6">
          <textarea
            class="w-full border border-gray-300 rounded-lg p-3 focus:outline-none focus:ring-2 focus:ring-primary focus:border-transparent"
            rows="3"
            placeholder="Add a comment..."
          ></textarea>
          <button class="mt-2 bg-primary text-white px-4 py-2 rounded-lg hover:bg-primary/90 transition">
            Post Comment
          </button>
        </div>
      </div>

      <!-- Related videos -->
      <div class="bg-white rounded-2xl shadow-lg p-6">
        <h2 class="text-xl font-bold text-gray-800 mb-4">Related Videos</h2>
        
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
          <div v-for="video in relatedVideos" :key="video.id" class="bg-gray-50 rounded-lg overflow-hidden hover:shadow-md transition">
            <div class="relative">
              <img
                :src="`/images/video-thumbnails/${video.id}.jpg`"
                alt="Video thumbnail"
                class="w-full h-40 object-cover"
              />
              <div class="absolute bottom-2 right-2 bg-black/70 text-white text-xs px-2 py-1 rounded">
                {{ video.duration }}
              </div>
            </div>
            <div class="p-3">
              <h3 class="font-medium text-gray-800 text-sm line-clamp-2">{{ video.title }}</h3>
              <p class="text-gray-500 text-xs mt-1">{{ video.views }} views</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>