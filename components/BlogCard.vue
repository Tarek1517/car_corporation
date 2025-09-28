<script setup>
defineProps({
  blog: {
    type: Object,
    required: true,
  },
});

// Helper functions
const formatMonth = (date) => {
  return new Date(date).toLocaleString("default", { month: "short" });
};

const formatDay = (date) => {
  return new Date(date).getDate();
};

const formatYear = (date) => {
  return new Date(date).getFullYear();
};

const formatRelativeDate = (date) => {
  const now = new Date();
  const publishDate = new Date(date);
  const diffTime = Math.abs(now - publishDate);
  const diffDays = Math.ceil(diffTime / (1000 * 60 * 60 * 24));

  if (diffDays === 1) return "Today";
  if (diffDays === 2) return "Yesterday";
  if (diffDays < 7) return `${diffDays - 1} days ago`;
  if (diffDays < 30) return `${Math.floor(diffDays / 7)} weeks ago`;
  return `${Math.floor(diffDays / 30)} months ago`;
};
</script>

<template>
  <div
    class="group bg-white rounded-2xl overflow-hidden flex flex-col h-full shadow-sm hover:shadow-xl transition-all duration-500 border border-gray-100/50 hover:border-gray-200/70"
  >
    <!-- Image Container - Fixed aspect ratio -->
    <div class="relative overflow-hidden h-56">
      <img
        :src="blog.image"
        :alt="blog.title"
        class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-110"
      />
      <div
        class="absolute inset-0 bg-gradient-to-t from-black/30 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500"
      ></div>

      <!-- Category -->
      <div class="absolute top-4 left-4">
        <span
          class="inline-flex items-center px-4 py-2 bg-gradient-to-r from-primary to-secondary text-white rounded-full text-sm font-semibold mb-4 shadow-lg"
        >
          {{ blog.category }}
        </span>
      </div>

      <!-- Publish Date -->
      <div class="absolute top-4 right-4">
        <div
          class="flex flex-col items-center justify-center bg-black/70 text-white rounded-lg py-2 px-3 backdrop-blur-sm"
        >
          <span class="text-xs font-semibold uppercase leading-none">{{
            formatMonth(blog.publishDate)
          }}</span>
          <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary font-bold">{{
            formatDay(blog.publishDate)
          }}</span>
          <span class="text-xs leading-none mt-1">{{
            formatYear(blog.publishDate)
          }}</span>
        </div>
      </div>
    </div>

    <!-- Content -->
    <div class="p-5 flex flex-col flex-grow">
      <!-- Title -->
      <h3
        class="text-lg md:text-2xl text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary font-bold"
      >
        {{ blog.title }}
      </h3>

      <!-- Excerpt -->
      <p
        class="text-gray-600 text-sm leading-relaxed max-w-xl"
      >
        {{ blog.excerpt }}
      </p>

      <!-- Footer -->
      <div
        class="flex items-center justify-between pt-4 border-t border-gray-100 mt-auto"
      >
        <div class="flex items-center space-x-2">
          <div class="relative">
            <img
              :src="blog.authorImage"
              :alt="blog.author"
              class="w-8 h-8 rounded-full object-cover ring-2 ring-white shadow"
            />
            <span
              class="absolute bottom-0 right-0 w-2.5 h-2.5 bg-green-400 rounded-full border border-white"
            ></span>
          </div>
          <div class="flex flex-col">
            <span class="text-sm font-medium text-gray-700">{{
              blog.author
            }}</span>
            <span class="text-xs text-gray-500">{{
              formatRelativeDate(blog.publishDate)
            }}</span>
          </div>
        </div>

        <a
          :href="blog.link"
          class="text-sm font-medium text-black hover:text-primary border border-primary/55 px-4 py-1 rounded-2xl flex items-center transition-all duration-300 group-hover:translate-x-1"
        >
          Read more
          <svg
            class="w-4 h-4 ml-1"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M14 5l7 7m0 0l-7 7m7-7H3"
            ></path>
          </svg>
        </a>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>