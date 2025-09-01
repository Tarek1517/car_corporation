<script setup>
const blogs = [
  {
    id: 1,
    title: "How to Import Your Dream Car Easily",
    category: "Guides",
    excerpt:
      "Learn step-by-step how to import cars from Japan with minimal hassle and maximum savings.",
    image: "/images/blog1.jpg",
    author: "John Doe",
    authorImage: "/images/avater1.png",
    link: "/blogs/how-to-import-car",
    publishDate: "2023-11-15"
  },
  {
    id: 2,
    title: "Top 5 Reliable Car Brands in 2025",
    category: "Reviews",
    excerpt:
      "We break down the most reliable brands this year, helping you choose wisely.",
    image: "/images/blog2.jpg",
    author: "Sarah Ali",
    authorImage: "/images/avater1.png",
    link: "/blogs/reliable-car-brands",
    publishDate: "2023-11-10"
  },
  {
    id: 3,
    title: "Why Auctions Are the Future of Car Buying",
    category: "Insights",
    excerpt:
      "Discover why car auctions are becoming increasingly popular worldwide.",
    image: "/images/counter.jpg",
    author: "Mike Lee",
    authorImage: "/images/avater1.png",
    link: "/blogs/car-auctions-future",
    publishDate: "2023-11-05"
  },
];
</script>

<template>
  <div class="w-full py-20 bg-gradient-to-br from-gray-50 to-white">
    <!-- Section Header -->
    <div class="text-center mb-14">
      <div
        class="inline-flex items-center px-4 py-2 bg-gradient-to-r from-primary to-secondary text-white rounded-full text-sm font-semibold mb-4 shadow-lg"
      >
        <Icon name="heroicons:newspaper" class="w-4 h-4 mr-2 animate-pulse" />
        Latest Articles
      </div>

      <h2 class="text-4xl md:text-5xl font-extrabold text-gray-900 mb-4">
        Our Recent
        <span
          class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary"
          >News & Articles</span
        >
      </h2>
      <p
        class="text-lg md:text-xl text-gray-600 max-w-4xl mx-auto leading-relaxed"
      >
        Discover expert insights, guides, and reviews to help you make informed
        decisions about your next vehicle.
      </p>
    </div>

    <!-- Blog Carousel -->
    <div class="container mx-auto px-6 mt-12">
      <UCarousel
        :items="blogs"
        loop
        auto-scroll
        :slides-per-view="3"
        :slide-to-scroll="1"
        class="overflow-visible"
        :ui="{ item: 'basis-full sm:basis-1/2 lg:basis-1/3 p-4' }"
      >
        <template #default="{ item }">
          <!-- Equal height wrapper -->
          <div class="h-[450px]">
            <BlogCard :blog="item" class="w-full h-full flex flex-col" />
          </div>
        </template>
      </UCarousel>
    </div>
  </div>
</template>

<style scoped>
/* Custom scrollbar for carousel */
:deep(.carousel-container) {
  scrollbar-width: thin;
  scrollbar-color: rgba(99, 102, 241, 0.3) transparent;
}

:deep(.carousel-container::-webkit-scrollbar) {
  height: 6px;
}

:deep(.carousel-container::-webkit-scrollbar-track) {
  background: transparent;
  border-radius: 3px;
}

:deep(.carousel-container::-webkit-scrollbar-thumb) {
  background: rgba(99, 102, 241, 0.3);
  border-radius: 3px;
}

:deep(.carousel-container::-webkit-scrollbar-thumb:hover) {
  background: rgba(99, 102, 241, 0.5);
}
</style>
