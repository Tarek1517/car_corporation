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
  departments: [
    { name: "Sales Department", email: "carcorpbd@gmail.com", phone: "+880-1704848771" },
    { name: "Customer Support", email: "carcorpbd@gmail.com", phone: "+880-1704848772" },
    { name: "Import & Logistics", email: "carcorpbd@gmail.com", phone: "+880-1704848773" },
  ]
};

const keyPersonnel = [
  { name: "Mr. Rakibul Islam", title: "Chief Executive Officer", image: "/images/avater1.png" },
  { name: "Ms. Farhana Akter", title: "Head of Sales", image: "/images/avater2.png" },
  { name: "Mr. Tanvir Ahmed", title: "Operations Manager", image: "/images/avater3.png" },
];

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
</script>

<template>
  <div class="bg-gray-50">
    <section class="relative h-[500px] w-full flex items-center justify-center text-center bg-cover bg-center" style="background-image: url('/images/showrooms.jpg');">
      <div class="absolute inset-0 bg-black/60"></div>
      <div class="relative z-10 px-4">
        <h1 class="text-4xl md:text-6xl font-extrabold text-white leading-tight mb-4">
          Our
            <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary drop-shadow">
            Head Office
          </span>
        </h1>
        <p class="text-lg md:text-xl text-gray-200 max-w-3xl mx-auto">
          The central hub of Car Corporation BD, where our vision and operations unite to drive excellence in the automotive industry.
        </p>
      </div>
    </section>
    <section class="py-20">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
          <div class="bg-white p-8 rounded-2xl shadow-lg border border-gray-200/80">
            <h2 class="text-3xl font-bold text-gray-900 mb-6">Corporate Headquarters</h2>
            <div class="space-y-4 text-gray-700">
              <div class="flex items-start">
                <Icon icon="mdi:map-marker-outline" class="w-6 h-6 text-primary mr-4 mt-1 flex-shrink-0" />
                <span>{{ headOffice.address }}</span>
              </div>
              <div class="flex items-center">
                <Icon icon="mdi:phone-outline" class="w-6 h-6 text-primary mr-4" />
                <span>{{ headOffice.tel }}</span>
              </div>
              <div class="flex items-center">
                <Icon icon="mdi:email-outline" class="w-6 h-6 text-primary mr-4" />
                <a :href="'mailto:' + headOffice.email" class="hover:text-primary">{{ headOffice.email }}</a>
              </div>
              <div class="flex items-center">
                <Icon icon="mdi:clock-time-four-outline" class="w-6 h-6 text-primary mr-4" />
                <span>{{ headOffice.workingHours }}</span>
              </div>
            </div>
            <div class="mt-8 pt-6 border-t border-gray-200">
              <h3 class="text-xl font-semibold text-gray-800 mb-4">Department Contacts</h3>
              <div class="space-y-3">
                <div v-for="dept in headOffice.departments" :key="dept.name" class="flex items-center justify-between text-sm">
                  <span class="font-medium text-gray-500">{{ dept.name }}:</span>
                  <a :href="'mailto:' + dept.email" class="text-gray-600 hover:text-primary">{{ dept.email }}</a>
                </div>
              </div>
            </div>
          </div>
<div class="rounded-2xl overflow-hidden shadow-2xl h-96">
  <iframe 
    src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d29207.81503222402!2d90.39532659893251!3d23.783837654739983!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3755c7df0c9880c9%3A0xfdd910ba6f9d8a60!2sCar%20Corporations%20BD!5e0!3m2!1sen!2sbd!4v1758102328671!5m2!1sen!2sbd" 
    width="100%" 
    height="100%" 
    style="border:0;" 
    allowfullscreen="" 
    loading="lazy">
  </iframe>
</div>
        </div>
      </div>
    </section>

    <section class="bg-white py-20">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <h2 class="text-3xl md:text-4xl font-bold text-center text-gray-900 mb-12">Meet Our Leaders</h2>
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
          <div v-for="person in keyPersonnel" :key="person.name" class="text-center">
            <img :src="person.image" :alt="person.name" class="w-40 h-40 rounded-full mx-auto mb-4 object-cover shadow-lg">
            <h3 class="text-xl font-semibold text-gray-900">{{ person.name }}</h3>
            <p class="text-primary">{{ person.title }}</p>
          </div>
        </div>
      </div>
    </section>

    <section class="py-20 bg-gray-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <h2 class="text-3xl md:text-4xl font-bold text-center text-gray-900 mb-12">Our Branch Offices</h2>
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-2 gap-8">
          <div v-for="branch in branchOffices" :key="branch.city" class="bg-white p-6 rounded-2xl shadow-md hover:shadow-xl transition-shadow duration-300">
            <h3 class="text-xl font-semibold text-primary mb-3">{{ branch.city }}</h3>
            <p class="text-gray-700 mb-2">{{ branch.address }}</p>
            <div class="text-sm text-gray-600">
              <span v-for="phone in branch.mob" :key="phone" class="block">{{ phone }}</span>
            </div>
            <a :href="branch.map" target="_blank" class="inline-block mt-4 text-primary font-semibold hover:underline">View on Map</a>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>