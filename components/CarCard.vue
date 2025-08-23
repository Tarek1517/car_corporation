<script setup>
const props = defineProps({
  car: {
    type: Object,
    required: true,
  },
});
</script>

<template>
  <NuxtLink :to="`/cars/${car.id}`" class="block group">
    <div
      class="bg-white rounded-2xl shadow-lg overflow-hidden transition-all duration-300 hover:shadow-xl border border-gray-100 h-full flex flex-col hover:-translate-y-1"
    >
      <!-- Header with type and favorite -->
      <div class="p-5 pb-3 flex justify-between items-start">
        <span
          class="px-3 py-1 bg-primary/10 text-primary text-xs font-semibold rounded-full"
        >
          {{ car.type }}
        </span>
        <button class="text-gray-400 hover:text-red-500 transition-colors p-1">
          <Icon name="heroicons:heart" class="w-5 h-5" />
        </button>
      </div>

      <!-- Car name -->
      <h3 class="px-5 text-xl font-bold text-gray-900 line-clamp-1 mb-3">
        {{ car.name }}
      </h3>

      <!-- Image -->
      <div class="relative h-48 mx-4 mb-4 overflow-hidden rounded-xl group">
        <!-- Car Image -->
        <img
          :src="car.image"
          :alt="car.name"
          class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-105"
          loading="lazy"
        />

        <!-- Gradient Hover Effect -->
        <div
          class="absolute inset-0 bg-gradient-to-t from-black/20 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300"
        ></div>

        <!-- Badge -->
        <div v-if="car.condition"
          class="absolute top-2 left-2 px-3 py-1 text-white bg-gradient-to-t from-primary to-secondary text-xs font-semibold rounded-full shadow-md"          
        >
          {{ car.condition }}
        </div>
      </div>

      <!-- Details grid -->
      <div class="grid grid-cols-3 justify-between mb-5">
        <div
          class="flex items-center text-start gap-2 p-3 bg-gray-50 rounded-xl transition-colors group-hover:bg-primary/5"
        >
          <div class="p-2 bg-primary/10 rounded-lg">
            <Icon name="line-md:calendar" class="w-4 h-4 text-primary" />
          </div>
          <div>
            <div class="text-xs text-gray-500 mb-1">Year</div>
            <div class="text-sm font-semibold text-gray-900">
              {{ car.year }}
            </div>
          </div>
        </div>

        <div
          class="flex items-center text-start gap-2 p-3 bg-gray-50 rounded-xl transition-colors group-hover:bg-primary/5"
        >
          <div class="p-2 bg-primary/10 rounded-lg">
            <Icon name="line-md:home" class="w-4 h-4 text-primary" />
          </div>
          <div>
            <div class="text-xs text-gray-500">Make</div>
            <div class="text-sm font-semibold text-gray-900">
              {{ car.make }}
            </div>
          </div>
        </div>

        <div
          class="flex items-center text-start p-3 gap-2 bg-gray-50 rounded-xl transition-colors group-hover:bg-primary/5"
        >
          <div class="p-2 bg-primary/10 rounded-lg">
            <Icon
              name="line-md:speedometer-loop"
              class="w-4 h-4 text-primary"
            />
          </div>
          <div>
            <div class="text-xs text-gray-500 mb-1">Mileage</div>
            <div class="text-sm font-semibold text-gray-900">32,405 mi</div>
          </div>
        </div>
      </div>

      <!-- Footer with price and CTA -->
      <div class="mt-auto p-5 pt-0 flex justify-between items-center">
        <div class="flex flex-col">
          <div class="text-xs text-gray-500">Starting at</div>
          <div class="text-2xl font-bold text-primary">$64,900</div>
        </div>
        <div
          class="flex items-center bg-gradient-to-t from-primary to-secondary text-white font-semibold text-sm px-4 py-2 rounded-lg transition-all duration-300 group-hover:shadow-lg group-hover:translate-x-1"
        >
          View Details
          <Icon
            name="heroicons:arrow-long-right"
            class="w-5 h-5 ml-2 transition-transform group-hover:translate-x-1"
          />
        </div>
      </div>
    </div>
  </NuxtLink>
</template>

<style scoped></style>
