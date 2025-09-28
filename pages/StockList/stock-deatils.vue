<script setup>
import { ref } from 'vue';
import { Icon } from '@iconify/vue';
const toast = useToast();
function showToast() {
  toast.add({
    title: 'Inquiry sent!',
    description: 'Your request was submitted successfully. We will contact you soon.',
    icon: 'mdi:check', 
    color: 'green', 
    timeout: 4000, 
  })
}
const vehicleData = ref({
  name: "2020 Toyota Prius",
  chassis: "ZVW51-6189222",
  price: "32,500 $",
  status: "Available",
  specifications: {
    stockId: "RRGI0905",
    brand: "TOYOTA",
    model: "PRIUS",
    year: "2020",
    mileage: "25,000 km",
    condition: "Used",
    fuelType: "Hybrid",
    transmission: "Automatic",
    engine: "1.8L Hybrid",
    exteriorColor: "Midnight Black Metallic",
    interiorColor: "Fabric - Black",
    vin: "JTDKARFU2L1234567",
    driveType: "FWD",
    fuelEconomy: "4.5 L/100km"
  },
  description: "This 2020 Toyota Prius is in excellent condition with low mileage. It features a hybrid engine, automatic transmission, and comes with a full service history. The vehicle is available for immediate purchase.",
  features: [
    "Touchscreen Infotainment System",
    "Backup Camera",
    "Advanced Safety Features",
    "Keyless Entry",
    "Climate Control",
    "Adaptive Cruise Control",
    "Lane Departure Alert",
    "Pre-Collision System"
  ],
  contact: {
    phone: "09613 787878",
    email: "carcorporationbd@gmail.com",
    address: "102, Shahid Tajuddin Ahmed Sarani, Tejgaon Industrial Area, Dhaka-1208s"
  },
  images: [
    "/images/car-yellow.png",
    "/images/car-yellow.png",
    "/images/car-yellow.png",
    "/images/car-yellow.png"
  ]
});

const activeImage = ref(0);

const setActiveImage = (index) => {
  activeImage.value = index;
};
</script>

<template>
  <section class="w-full bg-white text-gray-800 overflow-hidden">
    <div class="container mx-auto px-4 relative py-12">
      <div class="text-center mb-10">
        <h2 class="text-3xl text-gray-600 font-semibold">Stock Details</h2>

      </div>
      <div class="rounded-xl shadow-lg overflow-hidden max-w-7xl mx-auto">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 p-6">
          <div>
            <div class="rounded-lg overflow-hidden bg-gray-100 flex items-center justify-center h-96 mb-4">
              <img 
                :src="vehicleData.images[activeImage]" 
                :alt="vehicleData.name" 
                class="w-full h-full object-contain"
              />
            </div>
            
            <div class="grid grid-cols-4 gap-2">
              <div 
                v-for="(image, index) in vehicleData.images" 
                :key="index"
                @click="setActiveImage(index)"
                class="cursor-pointer rounded-md overflow-hidden h-20 bg-gray-100 flex items-center justify-center"
                :class="{'ring-2 ring-primary': activeImage === index}"
              >
                <img 
                  :src="image" 
                  :alt="`${vehicleData.name} view ${index + 1}`" 
                  class="w-full h-full object-cover"
                />
              </div>
            </div>
          </div>
          <div>
            <div class="flex justify-between items-start mb-4">
              <div>
                <h3 class="text-2xl font-bold">{{ vehicleData.name }}</h3>
                <p class="text-gray-600">{{ vehicleData.chassis }}</p>
              </div>
              <div class="flex space-x-2">
                <span class="bg-green-100 text-green-800 px-3 py-1 rounded-full text-sm font-medium">
                  {{ vehicleData.status }}
                </span>
              </div>
            </div>
            
            <div class="mb-6 flex items-baseline">
              <p class="text-3xl font-bold text-primary">{{ vehicleData.price }}</p>
              <span class="ml-2 text-gray-500">Negotiable</span>
            </div>
            <div class="grid grid-cols-3 gap-4 mb-6">
              <div class="bg-gray-50 rounded-lg p-3 text-center">
                <p class="text-sm text-gray-500">Year</p>
                <p class="font-semibold">{{ vehicleData.specifications.year }}</p>
              </div>
              <div class="bg-gray-50 rounded-lg p-3 text-center">
                <p class="text-sm text-gray-500">Mileage</p>
                <p class="font-semibold">{{ vehicleData.specifications.mileage }}</p>
              </div>
              <div class="bg-gray-50 rounded-lg p-3 text-center">
                <p class="text-sm text-gray-500">Fuel</p>
                <p class="font-semibold">{{ vehicleData.specifications.fuelType }}</p>
              </div>
            </div>
            <div class="flex space-x-3 mb-6">
              <button class="flex-1 bg-primary hover:bg-primary/90 text-white font-medium py-3 px-4 rounded-lg transition duration-300 flex items-center justify-center">
                <Icon icon="mdi:phone" class="w-5 h-5 mr-2" />
                Call Now
              </button>
              <button class="flex-1 bg-white border border-primary text-primary hover:bg-primary/5 font-medium py-3 px-4 rounded-lg transition duration-300 flex items-center justify-center">
                <Icon icon="mdi:message-text" class="w-5 h-5 mr-2" />
                WhatsApp
              </button>
            </div>
            <div class="mb-6">
              <h4 class="text-lg font-semibold mb-3 border-b pb-1">Description</h4>
              <p class="text-gray-700">{{ vehicleData.description }}</p>
            </div>
            <div>
              <h4 class="text-lg font-semibold mb-3 border-b pb-1">Key Features</h4>
              <div class="grid grid-cols-2 gap-2">
                <div v-for="(feature, index) in vehicleData.features" :key="index" class="flex items-center">
                  <Icon icon="mdi:check" class="w-4 h-4 text-green-500 mr-2" />
                  <span class="text-gray-700">{{ feature }}</span>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="p-6">
          <h3 class="text-xl font-bold mb-4">Detailed Specifications</h3>
          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
            <div class="flex border-b pb-2">
              <span class="text-gray-600 w-40">Stock ID:</span>
              <span class="font-medium">{{ vehicleData.specifications.stockId }}</span>
            </div>
            <div class="flex border-b pb-2">
              <span class="text-gray-600 w-40">Brand:</span>
              <span class="font-medium">{{ vehicleData.specifications.brand }}</span>
            </div>
            <div class="flex border-b pb-2">
              <span class="text-gray-600 w-40">Model:</span>
              <span class="font-medium">{{ vehicleData.specifications.model }}</span>
            </div>
            <div class="flex border-b pb-2">
              <span class="text-gray-600 w-40">Year:</span>
              <span class="font-medium">{{ vehicleData.specifications.year }}</span>
            </div>
            <div class="flex border-b pb-2">
              <span class="text-gray-600 w-40">Mileage:</span>
              <span class="font-medium">{{ vehicleData.specifications.mileage }}</span>
            </div>
            <div class="flex border-b pb-2">
              <span class="text-gray-600 w-40">Condition:</span>
              <span class="font-medium">{{ vehicleData.specifications.condition }}</span>
            </div>
            <div class="flex border-b pb-2">
              <span class="text-gray-600 w-40">Fuel Type:</span>
              <span class="font-medium">{{ vehicleData.specifications.fuelType }}</span>
            </div>
            <div class="flex border-b pb-2">
              <span class="text-gray-600 w-40">Transmission:</span>
              <span class="font-medium">{{ vehicleData.specifications.transmission }}</span>
            </div>
            <div class="flex border-b pb-2">
              <span class="text-gray-600 w-40">Engine:</span>
              <span class="font-medium">{{ vehicleData.specifications.engine }}</span>
            </div>
            <div class="flex border-b pb-2">
              <span class="text-gray-600 w-40">Exterior Color:</span>
              <span class="font-medium">{{ vehicleData.specifications.exteriorColor }}</span>
            </div>
            <div class="flex border-b pb-2">
              <span class="text-gray-600 w-40">Interior Color:</span>
              <span class="font-medium">{{ vehicleData.specifications.interiorColor }}</span>
            </div>
            <div class="flex border-b pb-2">
              <span class="text-gray-600 w-40">VIN:</span>
              <span class="font-medium">{{ vehicleData.specifications.vin }}</span>
            </div>
            <div class="flex border-b pb-2">
              <span class="text-gray-600 w-40">Drive Type:</span>
              <span class="font-medium">{{ vehicleData.specifications.driveType }}</span>
            </div>
            <div class="flex border-b pb-2">
              <span class="text-gray-600 w-40">Fuel Economy:</span>
              <span class="font-medium">{{ vehicleData.specifications.fuelEconomy }}</span>
            </div>
          </div>
        </div>
        
        <div class="bg-gray-50 p-6">
          <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
            <div>
              <h4 class="text-lg font-semibold mb-3">Contact Information</h4>
              <div class="space-y-3">
                <div class="flex items-center bg-white p-3 rounded-lg shadow-sm">
                  <div class="bg-primary/10 p-2 rounded-full mr-3">
                    <Icon icon="mdi:phone" class="w-5 h-5 text-primary" />
                  </div>
                  <div>
                    <p class="text-sm text-gray-500">Phone</p>
                    <p class="font-medium">{{ vehicleData.contact.phone }}</p>
                  </div>
                </div>
                <div class="flex items-center bg-white p-3 rounded-lg shadow-sm">
                  <div class="bg-primary/10 p-2 rounded-full mr-3">
                    <Icon icon="mdi:email" class="w-5 h-5 text-primary" />
                  </div>
                  <div>
                    <p class="text-sm text-gray-500">Email</p>
                    <p class="font-medium">{{ vehicleData.contact.email }}</p>
                  </div>
                </div>
                <div class="flex items-start bg-white p-3 rounded-lg shadow-sm">
                  <div class="bg-primary/10 p-2 rounded-full mr-3 mt-0.5">
                    <Icon icon="mdi:map-marker" class="w-5 h-5 text-primary" />
                  </div>
                  <div>
                    <p class="text-sm text-gray-500">Address</p>
                    <p class="font-medium">{{ vehicleData.contact.address }}</p>
                  </div>
                </div>
              </div>
            </div>
            
            <div>
              <h4 class="text-lg font-semibold mb-3">Send Inquiry</h4>
              <form class="space-y-4" >
                <div class="grid grid-cols-2 gap-3">
                  <div>
                    <input type="text" placeholder="Your Name" class="w-full px-4 py-3 border rounded-lg focus:ring-2 focus:ring-primary focus:border-transparent">
                  </div>
                  <div>
                    <input type="email" placeholder="Your Email" class="w-full px-4 py-3 border rounded-lg focus:ring-2 focus:ring-primary focus:border-transparent">
                  </div>
                </div>
                <div>
                  <input type="tel" placeholder="Your Phone" class="w-full px-4 py-3 border rounded-lg focus:ring-2 focus:ring-primary focus:border-transparent">
                </div>
                <div>
                  <textarea placeholder="Your Message" rows="3" class="w-full px-4 py-3 border rounded-lg focus:ring-2 focus:ring-primary focus:border-transparent"></textarea>
                </div>
                <UButton label="Submit Inquiry" class="w-full bg-primary hover:bg-primary/90 text-white font-medium py-3 px-6 rounded-lg transition duration-300 text-center" @click="showToast" />
                <!-- <button type="submit" class="w-full bg-primary hover:bg-primary/90 text-white font-medium py-3 px-6 rounded-lg transition duration-300">
                  Submit Inquiry
                </button> -->
              </form>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
