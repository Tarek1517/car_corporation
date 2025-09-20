<script setup>
import { Icon } from "@iconify/vue";

const headOffice = {
  city: "Dhaka",
  name: "Car Corporation HQ",
  address: "102, Shahid Tajuddin Ahmed Sarani, Tejgaon Industrial Area, Dhaka-1208",
  tel: "+880-2-8170902",
  email: "info@carcorporationbd.com",
  workingHours: "Sunday - Thursday: 9:00 AM - 6:00 PM",
  mob: ["+880-1704848771", "+880-1704848772"],
  map: "https://maps.google.com/?q=Tejgaon+Dhaka",
};

const branchOffices = [
  {
    city: "Chattogram",
    name: "Car Corporation Showroom",
    address: "F/2, Sk. Mujib Road, Agrabad, Chattogram",
    mob: ["+880-1322846204"],
    map: "https://maps.google.com/?q=Agrabad+Chattogram",
  },
  {
    city: "Sylhet",
    name: "Car Corporation Showroom",
    address: "31/3, North Kazitula, Electric Supply Road, Sylhet",
    mob: ["+880-1704848765"],
    map: "https://maps.google.com/?q=Kazitula+Sylhet",
  },
  {
    city: "Rajshahi",
    name: "Car Corporation Showroom",
    address: "248, Airport Road, Sopura, Boalia, Rajshahi",
    mob: ["+880-1729200822"],
    map: "https://maps.google.com/?q=Sopura+Rajshahi",
  },
  {
    city: "Khulna",
    name: "Car Corporation Showroom",
    address: "20-22, Majid Sarani, Sonadanga, Khulna",
    mob: ["+880-1729200822"],
    map: "https://maps.google.com/?q=Sonadanga+Khulna",
  },
];

// Combine head office + branches into one array
const showrooms = [
  {
    city: headOffice.city,
    name: headOffice.name,
    address: headOffice.address,
    tel: headOffice.tel,
    mob: headOffice.mob,
    map: headOffice.map,
  },
  ...branchOffices
];
</script>

<template>
  <section class="relative w-full overflow-hidden bg-gradient-to-br from-slate-50 via-white to-slate-100">
    <!-- Hero Banner -->
    <div class="relative h-[500px] md:h-[600px] w-full">
      <img src="/images/showrooms.jpg" alt="Showrooms Background" class="w-full h-full object-cover" />
      <div class="absolute inset-0 bg-black/50"></div>
      <div class="absolute inset-0 flex flex-col items-center justify-center text-center px-4 z-10">
        <h2 class="text-4xl md:text-5xl font-bold text-white drop-shadow-lg mb-4">
          Our
          <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary drop-shadow">
            Showrooms
          </span>
        </h2>
        <p class="text-lg md:text-xl text-gray-200 max-w-2xl">
          Explore our state-of-the-art showrooms across Bangladesh — where
          innovation meets elegance and every detail is crafted for an exceptional experience.
        </p>
      </div>
    </div>

    <!-- Products Section -->
    <div class="contain">
      <HomeProductsSection />
    </div>

    <!-- Showrooms Section -->
    <div class="relative py-16 bg-gradient-to-br from-slate-50 via-white to-slate-100">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <h2 class="text-3xl md:text-4xl font-bold text-center text-gray-900 mb-12">
          Our Showrooms Across Bangladesh
        </h2>

        <div class="grid gap-8 sm:grid-cols-2 lg:grid-cols-3">
          <div
            v-for="(item, idx) in showrooms"
            :key="idx"
            class="group bg-white shadow-md rounded-2xl p-6 border border-gray-100 hover:shadow-xl hover:scale-[1.02] transition-all duration-300"
          >
            <h3 class="text-lg font-semibold text-primary mb-3 uppercase tracking-wide flex items-center gap-2">
              <Icon name="mdi:map-marker" class="w-5 h-5 text-primary" />
              {{ item.city }}
            </h3>

            <p class="text-gray-800 font-medium mb-2 flex items-center gap-2">
              <Icon name="mdi:office-building-marker-outline" class="w-4 h-4 text-gray-500" />
              {{ item.name }}
            </p>

            <p class="text-gray-600 text-sm leading-relaxed mb-3 flex items-start gap-2">
              <Icon name="mdi:road-variant" class="w-4 h-4 text-gray-500 mt-0.5" />
              {{ item.address }}
            </p>

            <div v-if="item.tel" class="text-sm text-gray-700 mb-2 flex items-center gap-2">
              <Icon name="mdi:phone" class="w-4 h-4 text-gray-500" />
              <span>{{ item.tel }}</span>
            </div>

            <div class="text-sm text-gray-700 space-y-1">
              <span class="font-medium block">Mobile:</span>
              <div v-for="(num, i) in item.mob" :key="i" class="flex items-center gap-2">
                <Icon name="mdi:cellphone" class="w-4 h-4 text-gray-500" />
                <span>{{ num }}</span>
              </div>
            </div>

            <div v-if="item.map" class="mt-5">
              <a
                :href="item.map"
                target="_blank"
                class="inline-flex items-center gap-2 px-4 py-2 text-sm font-semibold text-white bg-gradient-to-r from-primary to-secondary rounded-lg hover:shadow-lg hover:translate-x-1 transition-all duration-300"
              >
                View on Map
                <Icon name="heroicons:arrow-long-right" class="w-5 h-5 transition-transform group-hover:translate-x-1" />
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Blog Section -->
    <HomeBlogSection />

    <!-- Trusted Icons -->
    <div class="mt-16 pt-12 border-t border-gray-200">
      <p class="text-center text-gray-500 text-sm mb-6">
        Trusted by automotive enthusiasts and businesses nationwide
      </p>
      <div class="flex flex-wrap justify-center gap-8 md:gap-12 opacity-60">
        <div class="h-8 w-auto grayscale hover:grayscale-0 transition-all">
          <Icon name="mdi:shield-check" class="w-full h-full text-primary" />
        </div>
        <div class="h-8 w-auto grayscale hover:grayscale-0 transition-all">
          <Icon name="mdi:medal" class="w-full h-full text-primary" />
        </div>
        <div class="h-8 w-auto grayscale hover:grayscale-0 transition-all">
          <Icon name="mdi:account-group" class="w-full h-full text-primary" />
        </div>
        <div class="h-8 w-auto grayscale hover:grayscale-0 transition-all">
          <Icon name="mdi:calendar-star" class="w-full h-full text-primary" />
        </div>
      </div>
    </div>
  </section>
</template>
