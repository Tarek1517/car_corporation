<script setup>
import { ref } from "vue";
import { Icon } from "@iconify/vue";

const form = ref({
  email: "",
});

const paymentMethods = [
  { name: "Visa", image: "/images/visa.png" },
  { name: "MasterCard", image: "/images/mastercard.png" },
  { name: "bKash", image: "/images/bkash1.png" },
  { name: "Nagad", image: "/images/nagad.jpg" },
  { name: "Rocket", image: "/images/rocket.png" },
];

</script>

<template>
  <section class="w-full relative overflow-hidden py-2 md:py-6 bg-gradient-to-br from-slate-50 via-white to-slate-100">
    <div class="absolute top-0 right-0 w-96 h-96 bg-primary/10 rounded-full -translate-y-1/3 translate-x-1/3 blur-3xl animate-pulse-slow"></div>
    <div class="absolute bottom-0 left-0 w-[32rem] h-[32rem] bg-secondary/10 rounded-full translate-y-1/3 -translate-x-1/3 blur-3xl animate-pulse-slow delay-1000"></div>
    <div class="absolute top-1/2 left-1/4 w-64 h-64 bg-primary/5 rounded-full blur-3xl animate-pulse-slow delay-500"></div>
    <div class="absolute inset-0 opacity-[0.03] bg-grid-pattern"></div>

    <div class="container mx-auto px-4 relative">
      <h2 class="text-3xl md:text-4xl font-bold text-center text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary mb-8">
        Instant Auction Sheet Verification Service of Japanese Car in Bangladesh
      </h2>

      <div class="max-w-6xl mx-auto bg-white rounded-2xl shadow-lg p-6 md:p-10 border border-gray-100 hover:shadow-xl transition-all duration-300">
        <h3 class="text-center text-2xl font-semibold text-gray-800 mb-6">
          Auction sheet verification by chassis number or VIN
        </h3>
        
        <div class="text-center font-semibold mb-12">
          <h4 class="text-center text-xl font-semibold text-gray-700 mt-2">
            Get the original Auction Sheet Verification by Car Corporation to buy the Japanese car with complete peace of mind!
          </h4>
        </div>

        <p class="text-gray-700 mb-4">
          At Car Corporation, we prioritize transparency and trust. Every vehicle listed on our platform comes with a verified auction sheet, ensuring you have all the information you need to make an informed decision.
        </p>
        
        <ul class="list-disc list-inside text-gray-700 space-y-2 mb-6">
          <li>Comprehensive vehicle details including mileage, condition, and history</li>
          <li>Inspection reports from certified mechanics</li>
          <li>Accurate pricing based on market trends and vehicle condition</li>
          <li>Verification of odometer readings and accident history</li>
          <li>Authenticity check of auction grade and condition ratings</li>
        </ul>
        
        <p class="text-gray-700 mb-8">
          Our commitment to providing verified auction sheets reflects our dedication to offering quality vehicles and exceptional service. Shop with confidence at Car Corporation, where transparency is key.
        </p>
<form 
  class="flex justify-center py-6 md:py-10"
>
  <div class="relative w-full max-w-xl flex">
    <Icon 
      icon="mdi:car" 
      class="absolute left-3 top-1/2 transform -translate-y-1/2 w-5 h-5 text-gray-400" 
    />
    <input 
      v-model="form.email" 
      type="text" 
      placeholder="Enter Chassis Number or VIN" 
      class="w-full pl-10 pr-2 py-2 rounded-l-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-700"
      required 
    />
    <button 
      type="submit"
      class="px-3 py-2 bg-gradient-to-r from-primary to-secondary text-white font-semibold rounded-r-lg shadow-lg hover:shadow-xl transition-all hover:scale-[1.02]"
    >
      Verify
    </button>
  </div>
</form>



        <div class="text-center">
          <p class="text-sm text-gray-500 mt-2">Instant verification delivered to your email</p>
        </div>
      </div>
      <div class="max-w-6xl mx-auto bg-white rounded-2xl shadow-lg p-6 md:p-10 border border-gray-100 hover:shadow-xl transition-all duration-300 mt-8">
        <h3 class="text-center text-2xl font-semibold text-gray-800 mb-6">
          Why Choose Our Auction Sheet Verification Service?
        </h3>
        
        <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-8">
          <div class="flex items-start">
            <div class="bg-primary/10 p-3 rounded-full mr-4">
              <Icon icon="mdi:check-circle" class="text-primary text-xl" />
            </div>
            <div>
              <h4 class="font-semibold text-lg mb-1 text-gray-700">Authentic Data</h4>
              <p class="text-gray-600">Direct access to Japanese auction house databases with real-time information</p>
            </div>
          </div>
          
          <div class="flex items-start">
            <div class="bg-primary/10 p-3 rounded-full mr-4">
              <Icon icon="mdi:timer" class="text-primary text-xl" />
            </div>
            <div>
              <h4 class="font-semibold text-lg mb-1 text-gray-700">Lightning Fast</h4>
              <p class="text-gray-600">Get verified reports in minutes, not days</p>
            </div>
          </div>
          
          <div class="flex items-start">
            <div class="bg-primary/10 p-3 rounded-full mr-4">
              <Icon icon="mdi:security" class="text-primary text-xl" />
            </div>
            <div>
              <h4 class="font-semibold text-lg mb-1 text-gray-700">Secure & Confidential</h4>
              <p class="text-gray-600">Your data is protected with enterprise-grade security</p>
            </div>
          </div>
          
          <div class="flex items-start">
            <div class="bg-primary/10 p-3 rounded-full mr-4">
              <Icon icon="mdi:headset" class="text-primary text-xl" />
            </div>
            <div>
              <h4 class="font-semibold text-lg mb-1 text-gray-700">Expert Support</h4>
              <p class="text-gray-600">Our specialists help you understand every detail in your report</p>
            </div>
          </div>
        </div>
        
        <p class="text-gray-700 text-center">
          Don't let uncertainty hold you back from owning your dream car. Use our auction sheet verification service today and drive away with confidence!
        </p>
      </div>

      <div class="max-w-6xl mx-auto bg-white rounded-2xl shadow-lg p-6 md:p-10 border border-gray-100 hover:shadow-xl transition-all duration-300 mt-8">
        <h3 class="text-center text-2xl font-semibold text-gray-800 mb-6">
          Secure Payment Options
        </h3>
        
<div class="flex flex-wrap justify-center gap-4 mb-6">
  <div v-for="method in paymentMethods" :key="method.name" class="flex flex-col items-center">
    <div class="bg-gray-100 hover:bg-gray-200 transition-colors">
      <img :src="method.image" :alt="method.name" class="w-24 h-24 object-contain" />
    </div>
    <span class="mt-2 text-sm text-gray-600">{{ method.name }}</span>
  </div>
</div>

        
        <div class="flex items-center justify-center">
          <Icon name="mdi:lock" class="text-green-500 mr-2" />
          <span class="text-green-600 font-medium">Secure 256-bit SSL encryption</span>
        </div>
        
        <p class="text-center text-gray-600 mt-4">
          We accept all major payment methods. Your transaction is fully secured and encrypted.
        </p>
      </div>
    </div>
  </section>
</template>