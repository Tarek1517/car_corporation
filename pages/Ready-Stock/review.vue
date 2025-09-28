<script setup>
import { ref, onMounted, computed } from 'vue'
import { useRoute } from 'vue-router'
import { useHead } from '@unhead/vue'
import { Icon } from '@iconify/vue'

const route = useRoute()
const videoId = ref(route.params.id || 'sample-video-1')

// Video data
const videoData = ref({
  id: 'video-1',
  title: "Toyota RAV4 Premium Edition - Full Review",
  video: "/images/video-1.mp4",
  thumbnail: "/images/rav4-1.jpg",
  description: "In-depth look at the Toyota RAV4 — exterior, interior, and performance. We test drive this amazing SUV and show you all its features.",
  duration: "7:22",
  views: "24.7K",
  likes: "1.2K",
  dislikes: "45",
  channel: {
    name: "Car Corporation Reviews",
    subscribers: "125K",
    avatar: "/images/avatars/channel-avatar.jpg"
  },
  uploadDate: "2 weeks ago"
})

const featuredVideo = ref({
  title: "Toyota RAV4 Premium Edition",
  video: "/images/video-1.mp4",
  thumbnail: "/images/rav4-1.jpg",
  description: "In-depth look at the Toyota RAV4 — exterior, interior, and performance.",
  duration: "7:22",
  views: "24.7K"
})

const isPlaying = ref(false)
const activeVideo = ref(null)
const newComment = ref('')

const playVideo = (id) => {
  activeVideo.value = id
  isPlaying.value = true
  // Get the video element and play it
  const videoElement = document.querySelector('video')
  if (videoElement) {
    videoElement.play()
  }
}

// Related videos
const relatedVideos = ref([
  {
    id: 'video-2',
    title: 'Toyota Corolla Cross Review 2023',
    thumbnail: '/images/crossred.jpeg',
    duration: '12:45',
    views: '8,923',
    channel: 'Car Corporation Reviews'
  },
  {
    id: 'video-3',
    title: 'Honda CR-V vs Toyota RAV4 Comparison',
    thumbnail: '/images/Rav4.jpeg',
    duration: '18:22',
    views: '15,671',
    channel: 'Car Corporation Reviews'
  },
  {
    id: 'video-4',
    title: '2024 Mazda CX-5 First Drive Experience',
    thumbnail: '/images/Harrier.jpeg',
    duration: '14:18',
    views: '9,845',
    channel: 'Car Corporation Reviews'
  }
])

const comments = ref([
  {
    id: 'comment-1',
    user: {
      name: 'Rahim Khan',
      avatar: '/images/avatars/user1.jpg'
    },
    text: 'Great review! The interior design looks amazing. Can you do a follow-up video on the fuel efficiency?',
    likes: 24,
    replies: 3,
    time: '1 day ago',
    liked: false
  },
  {
    id: 'comment-2',
    user: {
      name: 'Sara Ahmed',
      avatar: '/images/avatars/user2.jpg'
    },
    text: 'Very informative! I was considering buying this model and your review helped me make my decision.',
    likes: 18,
    replies: 1,
    time: '2 days ago',
    liked: false
  },
  {
    id: 'comment-3',
    user: {
      name: 'Ali Hassan',
      avatar: '/images/avatars/user3.jpg'
    },
    text: 'The acceleration test was impressive! How does it compare to the previous model?',
    likes: 12,
    replies: 5,
    time: '3 days ago',
    liked: false
  }
])

const likeComment = (commentId) => {
  const comment = comments.value.find(c => c.id === commentId)
  if (comment) {
    if (comment.liked) {
      comment.likes--
      comment.liked = false
    } else {
      comment.likes++
      comment.liked = true
    }
  }
}

const postComment = () => {
  if (newComment.value.trim()) {
    const comment = {
      id: 'comment-' + (comments.value.length + 1),
      user: {
        name: 'You',
        avatar: '/images/avatars/user-default.jpg'
      },
      text: newComment.value,
      likes: 0,
      replies: 0,
      time: 'Just now',
      liked: false
    }
    comments.value.unshift(comment)
    newComment.value = ''
  }
}

onMounted(() => {
  useHead({
    title: `${videoData.value.title} - Car Corporation`,
    meta: [
      { name: 'description', content: videoData.value.description },
      { property: 'og:title', content: `${videoData.value.title} - Car Corporation` },
      { property: 'og:description', content: videoData.value.description },
      { property: 'og:image', content: videoData.value.thumbnail }
    ]
  })
})
</script>

<template>
  <div class="min-h-screen bg-gradient-to-br from-slate-50 via-white to-slate-100">
    <div class="relative h-[400px] md:h-[500px] w-full">
      <img src="/images/review.jpg" alt="Showrooms Background" class="w-full h-full object-cover" />
      <div class="absolute inset-0 bg-black/50"></div>
      <div class="absolute inset-0 flex flex-col items-center justify-center text-center px-4 z-10">
        <h2 class="text-4xl md:text-5xl font-bold text-white drop-shadow-lg mb-4"> Video
          <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary drop-shadow">Reviews</span>
        </h2>
        <p class="text-lg md:text-xl text-gray-200 max-w-2xl">
          Watch detailed reviews of our premium vehicles — get an inside look at features, performance, and more.
        </p>
      </div>
    </div>

    <div class="container mx-auto px-4 py-8 max-w-6xl">
      <section class="mb-12">
        <div class="flex flex-col md:flex-row justify-between items-center md:items-center mb-6">
          <h2 class="text-3xl font-bold text-gray-800 mb-4 md:mb-0 text-center">Car Video</h2>
        </div>
        
        <div class="relative w-full aspect-video rounded-2xl overflow-hidden shadow-xl bg-black mb-6">
          <video 
            ref="videoPlayer"
            class="w-full h-full object-cover" 
            controls 
            :poster="featuredVideo.thumbnail"
            @play="isPlaying = true"
            @pause="isPlaying = false"
          >
            <source :src="featuredVideo.video" type="video/mp4" />
            Your browser does not support the video tag.
          </video>
          
          <div v-if="!isPlaying" 
               class="absolute inset-0 flex items-center justify-center bg-black/20 cursor-pointer"
               @click="playVideo('featured')">
            <div class="w-20 h-20 bg-white/90 rounded-full flex items-center justify-center hover:bg-white transition-transform hover:scale-105">
              <Icon icon="mdi:play" class="w-10 h-10 text-red-600 ml-1" />
            </div>
          </div>
        </div>
      </section>
      <section class="bg-white rounded-2xl shadow-lg p-6 mb-8">
        <h2 class="text-xl font-bold text-gray-800 mb-6">Review ({{ comments.length }})</h2>
      
        <div class="flex space-x-4 mb-8">
          <img
            src="/images/avater1.png"
            alt="Your avatar"
            class="w-10 h-10 rounded-full"
          />
          <div class="flex-1">
            <textarea
              v-model="newComment"
              class="w-full border border-gray-300 rounded-lg p-4 focus:outline-none focus:ring-2 focus:ring-primary focus:border-transparent resize-none"
              rows="3"
              placeholder="Add a comment..."
            ></textarea>
            <div class="flex justify-end mt-2">
              <button 
                @click="postComment"
                :disabled="!newComment.trim()"
                class="bg-primary text-white px-6 py-2 rounded-lg hover:bg-primary/90 transition-colors disabled:opacity-50 disabled:cursor-not-allowed"
              >
                Post Review
              </button>
            </div>
          </div>
        </div>
        
        <!-- Comments List -->
        <div class="space-y-6">
          <div v-for="comment in comments" :key="comment.id" class="border-b border-gray-100 pb-6 last:border-b-0">
            <div class="flex space-x-4">
              <img
                :src="comment.user.avatar"
                :alt="comment.user.name"
                class="w-10 h-10 rounded-full"
              />
              <div class="flex-1">
                <div class="flex items-center justify-between mb-2">
                  <h3 class="font-semibold text-gray-800">{{ comment.user.name }}</h3>
                  <span class="text-sm text-gray-500">{{ comment.time }}</span>
                </div>
                <p class="text-gray-700 mb-3">{{ comment.text }}</p>
                <div class="flex items-center space-x-4">
                  <button 
                    @click="likeComment(comment.id)"
                    :class="comment.liked ? 'text-primary' : 'text-gray-500'"
                    class="flex items-center space-x-1 hover:text-primary transition-colors"
                  >
                    <Icon :icon="comment.liked ? 'mdi:thumb-up' : 'mdi:thumb-up-outline'" class="w-4 h-4" />
                    <span class="text-sm">{{ comment.likes }}</span>
                  </button>
                  <button class="flex items-center space-x-1 text-gray-500 hover:text-gray-700 transition-colors">
                    <Icon icon="mdi:reply" class="w-4 h-4" />
                    <span class="text-sm">Reply</span>
                  </button>
                  <button class="flex items-center space-x-1 text-gray-500 hover:text-gray-700 transition-colors">
                    <Icon icon="mdi:flag" class="w-4 h-4" />
                    <span class="text-sm">Report</span>
                  </button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Related Videos -->
      <section class="bg-white rounded-2xl shadow-lg p-6">
        <h2 class="text-xl font-bold text-gray-800 mb-6">Related Videos</h2>
        
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
          <div 
            v-for="video in relatedVideos" 
            :key="video.id" 
            class="bg-gray-50 rounded-xl overflow-hidden hover:shadow-lg transition-all duration-300 cursor-pointer group"
          >
            <div class="relative">
              <img
                :src="video.thumbnail"
                :alt="video.title"
                class="w-full h-40 object-cover group-hover:scale-105 transition-transform duration-300"
              />
              <div class="absolute bottom-2 right-2 bg-black/80 text-white text-xs px-2 py-1 rounded">
                {{ video.duration }}
              </div>
              <div class="absolute inset-0 bg-black/0 group-hover:bg-black/10 transition-colors duration-300 flex items-center justify-center">
                <div class="w-12 h-12 bg-white/90 rounded-full flex items-center justify-center opacity-0 group-hover:opacity-100 transition-opacity duration-300">
                  <Icon icon="mdi:play" class="w-6 h-6 text-red-600 ml-0.5" />
                </div>
              </div>
            </div>
            <div class="p-4">
              <h3 class="font-semibold text-gray-800 text-sm line-clamp-2 mb-2 group-hover:text-primary transition-colors">
                {{ video.title }}
              </h3>
              <p class="text-gray-500 text-xs mb-1">{{ video.channel }}</p>
              <div class="flex justify-between items-center text-xs text-gray-500">
                <span>{{ video.views }} views</span>
              </div>
            </div>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<style scoped>
.line-clamp-2 {
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
}

.container {
  max-width: 1200px;
}

video {
  border-radius: 12px;
}

.bg-grid-pattern {
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 32 32' width='32' height='32' fill='none' stroke='rgb(15 23 42 / 0.04)'%3e%3cpath d='M0 .5H31.5V32'/%3e%3c/svg%3e");
}
</style>