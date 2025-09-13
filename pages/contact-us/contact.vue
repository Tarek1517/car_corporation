<script setup>
import { ref } from "vue";

const form = ref({
  name: "",
  email: "",
  phone: "",
  subject: "",
  message: "",
});

const handleSubmit = () => {
  console.log("Form Submitted:", form.value);
  alert("Thank you! We’ll get back to you soon.");
};
</script>

<template>
  <section class="w-full relative overflow-hidden py-2 md:py-6 bg-gradient-to-br from-slate-50 via-white to-slate-100">
    <div
      class="absolute top-0 right-0 w-96 h-96 bg-primary/10 -translate-y-1/3 translate-x-1/3 blur-3xl animate-pulse-slow">
    </div>
    <div
      class="absolute bottom-0 left-0 w-[32rem] h-[32rem] bg-secondary/10 translate-y-1/3 -translate-x-1/3 blur-3xl animate-pulse-slow delay-1000">
    </div>
    <div class="absolute top-1/2 left-1/4 w-64 h-64 bg-primary/5 blur-3xl animate-pulse-slow delay-500">
    </div>
    <div class="absolute inset-0 opacity-[0.03] bg-grid-pattern"></div>

    <div class="relative z-10">
      <div class="pb-12 relative">
        <div class="absolute top-0 left-0 w-64 h-64 bg-primary/5 blur-3xl -translate-x-1/2 -translate-y-1/2">
        </div>
        <div class="absolute bottom-0 right-0 w-80 h-80 bg-secondary/5 blur-3xl translate-x-1/3 translate-y-1/3">
        </div>

        <div class="relative z-10">
          <div class="text-center mb-16">
            <section class="relative bg-gradient-to-br from-slate-50 via-white to-slate-100">
              <div class="relative h-[400px] md:h-[500px] w-full overflow-hidden">
                <img src="../../public/images/counter.jpg" alt="Contact Us Background"
                  class="w-full h-full object-cover" />
                <div class="absolute inset-0 bg-black/30"></div>
                <div class="absolute inset-0 flex flex-col items-center justify-center text-center px-4 z-10">
                  <h2 class="text-4xl md:text-5xl font-bold text-white mb-4">
                    Contact
                    <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">
                      Us
                    </span>
                  </h2>
                  <p class="text-lg text-white max-w-2xl mx-auto">
                    Get in touch with our team for any inquiries about vehicle auctions, imports, or
                    dealership services.
                  </p>
                </div>
              </div>
            </section>
          </div>
        </div>

        <section class="py-6 bg-white">
          <div class="text-center items-center justify-center py-12">
            <p class="text-md text-gray-400">We’d Love to Hear From You</p>
            <h3 class="text-4xl text-gray-700 text-center">
              LET'S GET IN TOUCH!
            </h3>
            <div class="flex justify-center items-center py-2">
              <div class="border-b bg-primary w-20 border-primary border-2"></div>
              <div class="border-b bg-primary w-10 border-primary border-2"></div>
            </div>
          </div>
          <div class="container mx-auto px-4">
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4">
              <div
                class="bg-white p-6 flex flex-col items-center text-center shadow-sm border border-gray-100 hover:shadow-md transition-all duration-300 group">
                <div class="p-3 bg-primary/10 mb-4 group-hover:bg-primary/20 transition-colors duration-300">
                  <Icon name="mdi:map-marker" class="w-8 h-8 text-primary" />
                </div>
                <h4 class="font-bold text-lg mb-2 text-gray-800">ADDRESS</h4>
                <p class="text-sm text-gray-600">House 139 Rd Number 22, Dhaka 1212</p>
              </div>
              <div
                class="bg-white p-6 flex flex-col items-center text-center shadow-sm border border-gray-100 hover:shadow-md transition-all duration-300 group">
                <div class="p-3 bg-primary/10 mb-4 group-hover:bg-primary/20 transition-colors duration-300">
                  <Icon name="mdi:phone" class="w-8 h-8 text-primary" />
                </div>
                <h4 class="font-bold text-lg mb-2 text-gray-800">PHONE</h4>
                <p class="text-sm text-gray-600">+8801727-412340</p>
              </div>
              <div
                class="bg-white p-6 flex flex-col items-center text-center shadow-sm border border-gray-100 hover:shadow-md transition-all duration-300 group">
                <div class="p-3 bg-primary/10 mb-4 group-hover:bg-primary/20 transition-colors duration-300">
                  <Icon name="mdi:email-outline" class="w-8 h-8 text-primary" />
                </div>
                <h4 class="font-bold text-lg mb-2 text-gray-800">EMAIL</h4>
                <p class="text-sm text-gray-600">carcorpbd@gmail.com</p>
              </div>

              <div
                class="bg-white p-6 flex flex-col items-center text-center shadow-sm border border-gray-100 hover:shadow-md transition-all duration-300 group">
                <div class="p-3 bg-primary/10 mb-4 group-hover:bg-primary/20 transition-colors duration-300">
                  <Icon name="mdi:clock-outline" class="w-8 h-8 text-primary" />
                </div>
                <h4 class="font-bold text-lg mb-2 text-gray-800">BUSINESS HOURS</h4>
                <p class="text-sm text-gray-600">Mon-Sat: 9AM - 11PM</p>
              </div>
            </div>
          </div>
        </section>
      </div>
    </div>
    <section class="py-16 bg-gradient-to-br from-slate-50 via-white to-slate-100">
      <div class="max-w-5xl mx-auto px-6">
        <!-- Title -->
        <div class="text-center mb-12">
          <h2 class="text-3xl md:text-4xl font-bold text-gray-800">
            Contact <span class="text-primary">Car Corporation</span>
          </h2>
          <p class="mt-2 text-gray-600">
            Have questions? Reach out and we’ll be in touch shortly.
          </p>
        </div>

        <!-- Contact Form -->
        <div class="bg-white rounded-2xl shadow-xl p-8 md:p-12">
          <form @submit.prevent="handleSubmit" class="grid grid-cols-1 md:grid-cols-2 gap-6">
            <!-- Name -->
            <div class="col-span-1">
              <label class="block text-sm font-medium text-gray-700 mb-1">Name</label>
              <div class="relative">
                <span class="absolute left-3 top-3 text-gray-900">
                  <Icon name="mdi:account" class="w-8 h-8 text-primary" />
                </span>
                <input v-model="form.name" type="text" placeholder="Enter your name"
                  class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-500"
                  required />
              </div>
            </div>

            <!-- Email -->
            <div class="col-span-1">
              <label class="block text-sm font-medium text-gray-700 mb-1">Email</label>
              <div class="relative">
                <span class="absolute left-3 top-3 text-gray-400">
                  <Icon name="mdi:email" class="w-8 h-8 text-primary" />
                </span>
                <input v-model="form.email" type="email" placeholder="Enter your email"
                  class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-500"
                  required />
              </div>
            </div>

            <!-- Phone -->
            <div class="col-span-1">
              <label class="block text-sm font-medium text-gray-700 mb-1">Phone</label>
              <div class="relative">
                <span class="absolute left-3 top-3 text-gray-400">
                  <Icon name="mdi:phone" class="w-8 h-8 text-primary" />
                </span>
                <input v-model="form.phone" type="text" placeholder="Enter your phone"
                  class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-500" />
              </div>
            </div>

            <!-- Subject -->
            <div class="col-span-1">
              <label class="block text-sm font-medium text-gray-700 mb-1">Subject</label>
              <div class="relative">
                <span class="absolute left-3 top-3 text-gray-400">
                  <Icon name="mdi:message-text" class="w-8 h-8 text-primary" />
                </span>
                <input v-model="form.subject" type="text" placeholder="Enter subject"
                  class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-500" />
              </div>
            </div>

            <!-- Message -->
            <div class="col-span-1 md:col-span-2">
              <label class="block text-sm font-medium text-gray-700 mb-1">Message</label>
              <div class="relative">
                <span class="absolute left-3 top-3 text-gray-400">
                  <Icon name="mdi:note-text" class="w-8 h-8 text-primary" />
                </span>
                <textarea v-model="form.message" rows="4" placeholder="Write your message"
                  class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-500"></textarea>
              </div>
            </div>

            <!-- Submit -->
            <div class="col-span-1 md:col-span-2 flex justify-center">
              <button type="submit"
                class="px-8 py-3 bg-primary text-white font-semibold rounded-xl shadow-md hover:bg-primary/90 transition">
                Send Message
              </button>
            </div>
          </form>
        </div>
      </div>
    </section>
  </section>
</template>

<style>
@keyframes pulse-slow {

  0%,
  100% {
    opacity: 0.4;
  }

  50% {
    opacity: 0.7;
  }
}

.animate-pulse-slow {
  animation: pulse-slow 8s cubic-bezier(0.4, 0, 0.6, 1) infinite;
}

.bg-grid-pattern {
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 32 32' width='32' height='32' fill='none' stroke='rgb(15 23 42 / 0.05)'%3e%3cpath d='M0 .5H31.5V32'/%3e%3c/svg%3e");
}

/* Smooth transitions for all elements */
* {
  transition-property: color, background-color, border-color, transform, box-shadow;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 300ms;
}
</style>