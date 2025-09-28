<script setup>
import { Icon } from '@iconify/vue';
import { ref } from 'vue';
import CarOverview from './carOverview.vue';
import DutyCalculator from './dutyCalculator.vue';
import CarCard from '~/components/CarCard.vue';

const cars = ref([
  { src: "/images/crossred.jpeg" },
  { src: "/images/Rav4.jpeg" },
  { src: "/images/rav4-1.jpg" },
  { src: "/images/rav4-2.png" },
  { src: "/images/rav4-3.jpg" },
]);

const showModal = ref(false);
const activeImage = ref(null);

const openModal = (src) => {
  activeImage.value = src;
  showModal.value = true;
};

const closeModal = () => {
  showModal.value = false;
  activeImage.value = null;
};

const carsDetails = [
    {
        id: 1,
        type: "SUV",
        name: "Toyota RAV4",
        year: 2022,
        make: "Toyota",
        image: "/images/Rav4.jpeg",
        price: "$32,450",
        mileage: "18,240 mi",
    },
    {
        id: 2,
        type: "SUV",
        name: "Toyota Corolla Cross",
        year: 2022,
        make: "Toyota",
        image: "/images/cross 1.jpeg",
        price: "$28,900",
        mileage: "12,150 mi",
    },
     {
    id: 3,
    type: "SUV",
    name: "Toyota Harrier",
    year: 2021,
    make: "Toyota",
    image: "/images/Harrier.jpeg",
    price: "$36,750",
    mileage: "22,405 mi",
   
  },
];

const comments = ref([
    {
        id: 1,
        author: 'Rahim Khan',
        date: new Date('2024-09-05'),
        content: 'Excellent guide! I used Car Corporation for my Toyota Noah import from Japan auction. The shipping and customs process was seamless thanks to their team.',
        rating: 5
    },
    {
        id: 2,
        author: 'Ayesha Rahman',
        date: new Date('2024-09-08'),
        content: 'This helped me avoid common pitfalls with BRTA registration. Highly recommend their inspection services for JDM cars!',
        rating: 4
    }
]);

const newComment = ref({
    author: '',
    email: '',
    content: '',
    rating: 0 
});

const submitComment = () => {
    if (newComment.value.author && newComment.value.email && newComment.value.content && newComment.value.rating > 0) {
        comments.value.push({
            id: comments.value.length + 1,
            author: newComment.value.author,
            date: new Date(),
            content: newComment.value.content,
            avatar: '/images/default-avatar.png',
            rating: newComment.value.rating
        });

        newComment.value = {
            author: '',
            email: '',
            content: '',
            rating: 0
        };

        alert('Your review has been submitted! We\'ll review it for our Bangladesh car import community.');
    } else {
        alert('Please fill in all fields and provide a rating');
    }
};

</script>

<template>
  <section class="w-full relative overflow-hidden bg-gradient-to-br from-slate-50 via-white to-slate-100">
    <section class="relative z-10 py-2">
      <div class="min-h-screen bg-gray-50">
        <div class="container mx-auto px-4 py-2">
          <div class="mb-8">
            <h1 class="text-3xl font-bold text-gray-900">Toyota RAV4</h1>
            <div class="flex items-center mt-2">
              <span class="text-3xl font-bold text-primary">$32,450</span>
              <span class="ml-4 bg-red-100 text-primary px-3 py-1 rounded-full text-sm">Used</span>
            </div>
          </div>

          <div class="text-start mx-auto font-normal text-gray-700">
            4.0 D5 PowerPulse Momentum 5dr AWD Geartronic Estate
          </div>
          <div class="flex items-center mx-auto font-normal py-2 gap-4">
            <span class="bg-red-100 text-primary px-3 py-1 rounded-full text-sm flex font-semibold">
              <Icon icon="line-md:calendar" class="w-5 h-5 text-red-600 mr-2" /> 2022
            </span>
            <span class="bg-red-100 text-primary px-3 py-1 rounded-full text-sm flex font-semibold">
              <Icon icon="line-md:home" class="w-5 h-5 text-red-600 mr-2" /> Tokyo
            </span>
            <span class="bg-red-100 text-primary px-3 py-1 rounded-full text-sm flex font-semibold">
              <Icon icon="line-md:speedometer-loop" class="w-5 h-5 text-red-600 mr-2" /> 18,240 mi
            </span>
            <span class="bg-red-100 text-primary px-3 py-1 rounded-full text-sm flex font-semibold">
              <Icon icon="mdi:gas-station" class="w-5 h-5 text-red-600 mr-2" /> Petrol
            </span>
          </div>
          <section class="max-w-7xl mx-auto p-4">
            <div class="grid grid-cols-1 md:grid-cols-3 gap-3">
              <div class="relative md:col-span-2">
                <img :src="cars[0].src" class="w-full h-[420px] object-cover rounded-lg cursor-pointer" alt="Main Car"
                  @click="openModal(cars[0].src)" />
              </div>
              <div class="grid grid-cols-2 gap-3">
                <div v-for="(car, index) in cars.slice(1)" :key="index" class="relative">
                  <img :src="car.src" class="w-full h-[200px] object-cover rounded-lg cursor-pointer" alt="Car image"
                    @click="openModal(car.src)" />
                </div>
              </div>
            </div>
          </section>
        </div>
      </div>
    </section>
    <div v-if="showModal" class="fixed inset-0 z-50 bg-black/70 flex items-center justify-center p-4">
      <div class="relative max-w-4xl w-full">
        <button class="absolute top-3 right-3 bg-white p-2 rounded-full shadow hover:bg-gray-200" @click="closeModal">
          <Icon icon="line-md:close" class="w-6 h-6 text-gray-700" />
        </button>
        <img :src="activeImage" class="w-full max-h-[90vh] object-contain rounded-lg" alt="Preview" />
      </div>
    </div>
    <section class="flex items-center justify-center">
      <div class="max-w-7xl mx-auto p-4">
        <div class="relative z-10">
          <div class="mb-8">
            <CarOverview />
          </div>
        </div>
      </div>
    </section>
    <div class="items-center mx-auto h-[1px] bg-gradient-to-r from-gray-300 via-gray-400 to-gray-300 my-8 max-w-7xl">
    </div>
    <section class="flex items-start justify-start max-w-7xl mx-auto p-4">
      <div class="mb-8 text-start">
        <h2 class="text-3xl font-bold text-gray-800 mb-2">Description</h2>
        <p class="text-start py-2 text-gray-600">
          Quisque imperdiet dignissim enim dictum finibus. Sed consectetutr convallis enim eget laoreet. Aenean vitae
          nisl mollis, porta risus vel, dapibus lectus. Etiam ac suscipit eros, eget maximus
        </p>
        <p class="text-start py-2 text-gray-600">
          Etiam sit amet ex pharetra, venenatis ante vehicula, gravida sapien. Fusce eleifend vulputate nibh, non cursus
          augue placerat pellentesque. Sed venenatis risus nec felis mollis, in pharetra urna euismod. Morbi aliquam ut
          turpis sit amet ultrices. Vestibulum mattis blandit nisl, et tristique elit scelerisque nec. Fusce eleifend
          laoreet dui eget aliquet. Ut rutrum risus et nunc pretium scelerisque.
        </p>
      </div>
    </section>
    <div class="items-center mx-auto h-[1px] bg-gradient-to-r from-gray-300 via-gray-400 to-gray-300 my-8 max-w-7xl">
    </div>
    <section class="flex items-start justify-start max-w-7xl mx-auto p-4">
      <div class="mb-8 text-start">
        <h2 class="text-3xl font-bold text-gray-800 mb-2">Features</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8 mt-6">
          <div>
            <h3 class="text-xl font-semibold text-gray-700 mb-4">Interior</h3>
            <ul class="space-y-2">
              <li class="flex items-center text-gray-600">
                <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Air Conditioner
              </li>
              <li class="flex items-center text-gray-600">
                <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Digital Odometer
              </li>
              <li class="flex items-center text-gray-600">
                <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Heater
              </li>
              <li class="flex items-center text-gray-600">
                <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Leather Seats
              </li>
              <li class="flex items-center text-gray-600">
                <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Panoramic Moonroof
              </li>
              <li class="flex items-center text-gray-600">
                <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Tachometer
              </li>
              <li class="flex items-center text-gray-600">
                <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Touchscreen Display
              </li>
            </ul>
          </div>
          <div>
            <h3 class="text-xl font-semibold text-gray-700 mb-4">Safety</h3>
            <ul class="space-y-2">
              <li class="flex items-center text-gray-600">
                <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Anti-lock Braking
              </li>
              <li class="flex items-center text-gray-600">
                <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Brake Assist
              </li>
              <li class="flex items-center text-gray-600">
                <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Child Safety Locks
              </li>
              <li class="flex items-center text-gray-600">
                <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Driver Air Bag
              </li>
              <li class="flex items-center text-gray-600">
                <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Power Door Locks
              </li>
              <li class="flex items-center text-gray-600">
                <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Stability Control
              </li>
              <li class="flex items-center text-gray-600">
                <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Traction Control
              </li>
            </ul>
          </div>
          <div>
            <h3 class="text-xl font-semibold text-gray-700 mb-4">Exterior</h3>
            <ul class="space-y-2">
              <li class="flex items-center text-gray-600">
                <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Fog Lights Front
              </li>
              <li class="flex items-center text-gray-600">
                <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Rain Sensing Wiper
              </li>
              <li class="flex items-center text-gray-600">
                <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Rear Spoiler
              </li>
              <li class="flex items-center text-gray-600">
                <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Windows - Electric
              </li>
            </ul>
          </div>
          <div>
            <h3 class="text-xl font-semibold text-gray-700 mb-4">Comfort & Convenience</h3>
            <ul class="space-y-2">
              <li class="flex items-center text-gray-600">
                <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Android Auto
              </li>
              <li class="flex items-center text-gray-600">
                <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Apple CarPlay
              </li>
              <li class="flex items-center text-gray-600">
                <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Bluetooth
              </li>
              <li class="flex items-center text-gray-600">
                <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> HomeLink
              </li>
              <li class="flex items-center text-gray-600">
                <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Power Steering
              </li>
              <li class="flex items-center text-gray-600">
                <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Vanity Mirror
              </li>
            </ul>
          </div>
        </div>
      </div>
    </section>
    <div class="items-center mx-auto h-[1px] bg-gradient-to-r from-gray-300 via-gray-400 to-gray-300 my-8 max-w-7xl">
    </div>
    <section class="flex items-start justify-start max-w-7xl mx-auto p-4">
      <div class="mb-8 text-start w-full">
        <h2 class="text-3xl font-bold text-gray-800 mb-2">Dimensions & Capacity</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-x-16 gap-y-4 mt-6">
          <div class="flex justify-between">
            <span class="text-gray-600">Length</span>
            <span class="font-semibold text-gray-800">4550mm</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Width</span>
            <span class="font-semibold text-gray-800">2140mm</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Height</span>
            <span class="font-semibold text-gray-800">1550mm</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Width (including mirrors)</span>
            <span class="font-semibold text-gray-800">2140mm</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Wheelbase</span>
            <span class="font-semibold text-gray-800">2584mm</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Gross Vehicle Weight (kg)</span>
            <span class="font-semibold text-gray-800">1850</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Height (including roof rails)</span>
            <span class="font-semibold text-gray-800">1876mm</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Max. Loading Weight (kg)</span>
            <span class="font-semibold text-gray-800">1200</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Luggage Capacity (Seats Up - Litres)</span>
            <span class="font-semibold text-gray-800">350</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Max. Roof Load (kg)</span>
            <span class="font-semibold text-gray-800">350</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Luggage Capacity (Seats Down - Litres)</span>
            <span class="font-semibold text-gray-800">850</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">No. of Seats</span>
            <span class="font-semibold text-gray-800">5</span>
          </div>
        </div>
        <div
          class="items-center mx-auto h-[1px] bg-gradient-to-r from-gray-300 via-gray-400 to-gray-300 my-8 max-w-7xl">
        </div>
        <h2 class="text-3xl font-bold text-gray-800 mb-2 mt-12">Engine and Transmission</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-x-16 gap-y-4 mt-6">
          <div class="flex justify-between">
            <span class="text-gray-600">Fuel Tank Capacity (Litres)</span>
            <span class="font-semibold text-gray-800">85</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Minimum Kerbweight (kg)</span>
            <span class="font-semibold text-gray-800">350</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Max. Towing Weight - Braked (kg)</span>
            <span class="font-semibold text-gray-800">1000</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Turning Circle - Kerb to Kerb (m)</span>
            <span class="font-semibold text-gray-800">5000</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Max. Towing Weight - Unbraked (kg)</span>
            <span class="font-semibold text-gray-800">1200</span>
          </div>
        </div>
      </div>
    </section>
        <div class="items-center mx-auto h-[1px] bg-gradient-to-r from-gray-300 via-gray-400 to-gray-300 my-8 max-w-7xl">
    </div>
<section class="mt-12 pt-8 max-w-7xl justify-center items-center mx-auto">
    <h3 class="text-2xl font-semibold mb-6 text-gray-500">Reviews ({{ comments.length }})</h3>

    <div class="bg-white p-6 rounded-lg shadow mb-8">
        <h4 class="font-semibold mb-4 text-gray-500">Leave a Review</h4>
        <form @submit.prevent="submitComment">
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mb-4">
                <div>
                    <label for="name" class="block text-sm font-medium text-gray-700 mb-1">Name</label>
                    <input v-model="newComment.author" type="text" id="name"
                        class="w-full p-2 border rounded focus:ring-2 focus:ring-primary focus:border-transparent transition-all text-gray-500"
                        placeholder="Enter your Name" required />
                </div>
                <div>
                    <label for="email" class="block text-sm font-medium text-gray-700 mb-1">Email</label>
                    <input v-model="newComment.email" type="email" id="email"
                        class="w-full p-2 border rounded focus:ring-2 focus:ring-primary focus:border-transparent transition-all text-gray-500"
                        placeholder="Enter you Email" required />
                </div>
            </div>
            
            <div class="mb-4">
                <label class="block text-sm font-medium text-gray-700 mb-2">Your Rating</label>
                <div class="flex items-center space-x-1">
                    <button 
                        v-for="star in 5" 
                        :key="star"
                        type="button"
                        @click="newComment.rating = star"
                        class="focus:outline-none transition-transform hover:scale-110"
                    >
                        <Icon 
                            :icon="star <= newComment.rating ? 'mdi:star' : 'mdi:star-outline'" 
                            class="w-8 h-8" 
                            :class="star <= newComment.rating ? 'text-yellow-400' : 'text-gray-300'"
                        />
                    </button>
                    <span class="ml-2 text-sm text-gray-600">{{ newComment.rating }}/5</span>
                </div>
            </div>

            <div class="mb-4">
                <label for="comment" class="block text-sm font-medium text-gray-700 mb-1">Comment</label>
                <textarea v-model="newComment.content" id="comment" rows="4"
                    class="w-full p-2 border rounded focus:ring-2 focus:ring-primary focus:border-transparent transition-all text-gray-500"
                    placeholder="Give Your Comment here" required></textarea>
            </div>
            <button type="submit"
                class="bg-primary text-white py-2 px-6 rounded hover:bg-primary/90 transition flex items-center gap-2">
                <Icon icon="mdi:send-variant" class="w-5 h-5" />
                Submit Review
            </button>
        </form>
    </div>

    <div class="space-y-6">
        <div v-for="comment in comments" :key="comment.id" class="bg-white p-6 rounded-lg shadow">
            <div class="flex items-start gap-4">

                <div class="flex-1">
                    <div class="flex items-center gap-2 mb-2">
                        <h4 class="font-semibold">{{ comment.author }}</h4>
                        <span class="text-sm text-gray-500">{{ comment.date.toLocaleDateString() }}</span>
                    </div>
                    
                    <div class="flex items-center mb-3">
                        <div class="flex items-center space-x-1">
                            <Icon 
                                v-for="star in 5" 
                                :key="star"
                                :icon="star <= comment.rating ? 'mdi:star' : 'mdi:star-outline'" 
                                class="w-5 h-5" 
                                :class="star <= comment.rating ? 'text-yellow-400' : 'text-gray-300'"
                            />
                        </div>
                        <span class="ml-2 text-sm text-gray-600">{{ comment.rating }}/5</span>
                    </div>
                    
                    <p class="text-gray-700">{{ comment.content }}</p>
                </div>
            </div>
        </div>
    </div>
    
</section>
    <div class="items-center mx-auto h-[1px] bg-gradient-to-r from-gray-300 via-gray-400 to-gray-300 my-8 max-w-7xl">
    </div>
<section class="max-w-7xl mx-auto p-4">
  <h2 class="text-3xl font-bold text-gray-800 mb-6">Related Cars</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 mb-16">
        <CarCard
          v-for="car in carsDetails"
          :key="car.id"
          :car="car"
          class="w-full transform hover:scale-105 transition-transform duration-300"
        />
      </div>
</section>
  </section>
</template>
