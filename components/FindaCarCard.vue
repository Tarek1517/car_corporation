<script setup>
const props = defineProps({
  car: {
    type: Object,
    required: true,
  },
});
</script>
<template>
    <NuxtLink to="/cars">
        <div
            class="bg-white rounded-2xl shadow-lg overflow-hidden transition-all duration-300 hover:shadow-xl border border-gray-100 h-full flex flex-col hover:-translate-y-1">
            <div class="p-5 pb-3 flex justify-between items-start">
                <span class="px-3 py-1 bg-primary/10 text-primary text-xs font-semibold rounded-full">
                    {{ car.vehicle }}
                </span>
                <span class="px-3 py-1 bg-primary/10 text-primary text-xs font-semibold rounded-full">
                    {{ car.type }}
                </span>
                <span class="px-3 py-1 bg-primary/10 text-primary text-xs font-semibold rounded-full">
                    {{ car.engine }}
                </span>
                <span class="px-3 py-1 bg-primary/10 text-primary text-xs font-semibold rounded-full">
                    {{ car.fuel }}
                </span>
                <span class="px-3 py-1 bg-primary/10 text-primary text-xs font-semibold rounded-full">
                    {{ car.gear }}
                </span>
                <span class="px-3 py-1 bg-primary/10 text-primary text-xs font-semibold rounded-full">
                    {{ car.vin }}
                </span>
            </div>
            <div class="p-5 pb-3 flex justify-between items-end">
                <span class="px-3 py-1 bg-primary/10 text-primary text-xs font-semibold rounded-full">
                    {{ code.code }}
                </span>
                                <span class="px-3 py-1 bg-primary/10 text-primary text-xs font-semibold rounded-full">
                    {{ code.condition }}
                </span>
                                <span class="px-3 py-1 bg-primary/10 text-primary text-xs font-semibold rounded-full">
                    {{ code.year }}
                </span>
                                <span class="px-3 py-1 bg-primary/10 text-primary text-xs font-semibold rounded-full">
                    {{ code.color }}
                </span>
                                <span class="px-3 py-1 bg-primary/10 text-primary text-xs font-semibold rounded-full">
                    {{ code.mileage }}
                </span>
            </div>
            <h3 class="px-5 text-xl font-bold text-gray-900 line-clamp-1 mb-3">
                {{ car.name }}
            </h3>
        </div>
        <div class="flex items-center text-white font-semibold text-sm px-4 py-2 transition-all duration-300 group-hover:shadow-lg group-hover:translate-x-1">
            {{ car.stock }}
        </div>
        <div class="flex items-center text-gray-700 font-semibold text-sm px-4 py-2 transition-all duration-300 group-hover:shadow-lg group-hover:translate-x-1">
            Call for price
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
    </NuxtLink>
</template>

<style scoped></style>