<script setup>
import { Icon } from "@iconify/vue";

const headOffice = {
  city: "Dhaka",
  name: "Car Corporation HQ",
  address: "102, Shahid Tajuddin Ahmed Sarani, Tejgaon Industrial Area, Dhaka-1208",
  tel: "+880-2-8170902",
  email: "carcorporationbd@gmail.com",
  workingHours: "Sunday - Thursday: 9:00 AM - 6:00 PM",
  mob: ["+880-1704848771", "+880-1704848772"],
  map: "https://maps.google.com/?q=Tejgaon+Dhaka",
  departments: [
    { name: "Sales Department", email: "carcorpbd@gmail.com", phone: "+880-1704848771" },
    { name: "Customer Support", email: "carcorpbd@gmail.com", phone: "+880-1704848772" },
    { name: "Import & Logistics", email: "carcorpbd@gmail.com", phone: "+880-1704848773" },
  ]
};
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
                  <span class="font-medium">{{ dept.name }}:</span>
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
                  <Icon icon="mdi:map-marker" class="w-4 h-4 text-primary" />
                </div>
                <h4 class="font-bold text-lg mb-2 text-gray-800">ADDRESS</h4>
                <p class="text-sm text-gray-600">House 139 Rd Number 22, Dhaka 1212</p>
              </div>
              <div
                class="bg-white p-6 flex flex-col items-center text-center shadow-sm border border-gray-100 hover:shadow-md transition-all duration-300 group">
                <div class="p-3 bg-primary/10 mb-4 group-hover:bg-primary/20 transition-colors duration-300">
                  <Icon icon="mdi:phone" class="w-4 h-4 text-primary" />
                </div>
                <h4 class="font-bold text-lg mb-2 text-gray-800">PHONE</h4>
                <p class="text-sm text-gray-600">+8801727-412340</p>
              </div>
              <div
                class="bg-white p-6 flex flex-col items-center text-center shadow-sm border border-gray-100 hover:shadow-md transition-all duration-300 group">
                <div class="p-3 bg-primary/10 mb-4 group-hover:bg-primary/20 transition-colors duration-300">
                  <Icon icon="mdi:email-outline" class="w-4 h-4 text-primary" />
                </div>
                <h4 class="font-bold text-lg mb-2 text-gray-800">EMAIL</h4>
                <p class="text-sm text-gray-600">carcorpbd@gmail.com</p>
              </div>

              <div
                class="bg-white p-6 flex flex-col items-center text-center shadow-sm border border-gray-100 hover:shadow-md transition-all duration-300 group">
                <div class="p-3 bg-primary/10 mb-4 group-hover:bg-primary/20 transition-colors duration-300">
                  <Icon icon="mdi:clock-outline" class="w-4 h-4 text-primary" />
                </div>
                <h4 class="font-bold text-lg mb-2 text-gray-800">BUSINESS HOURS</h4>
                <p class="text-sm text-gray-600">Mon-Sat: 9AM - 11PM</p>
              </div>
            </div>
          </div>
        </section>
            <section class="py-16 bg-gradient-to-br from-slate-50 via-white to-slate-100">
      <div class="max-w-5xl mx-auto px-6">
        <div class="text-center mb-12">
          <h2 class="text-3xl md:text-4xl font-bold text-gray-800">
            Contact <span class="text-primary">Car Corporation</span>
          </h2>
          <p class="mt-2 text-gray-600">
            Have questions? Reach out and we’ll be in touch shortly.
          </p>
        </div>

        <div class="bg-white rounded-2xl shadow-xl p-8 md:p-12">
          <form @submit.prevent="handleSubmit" class="grid grid-cols-1 md:grid-cols-2 gap-6">
            <div class="col-span-1">
              <label class="block text-sm font-medium text-gray-700 mb-1">Name</label>
              <div class="relative">
                <span class="absolute left-3 top-3 text-gray-900">
                  <Icon icon="mdi:account" class="w-4 h-4 text-primary" />
                </span>
                <input v-model="form.name" type="text" placeholder="Enter your name"
                  class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-500"
                  required />
              </div>
            </div>

            <div class="col-span-1">
              <label class="block text-sm font-medium text-gray-700 mb-1">Email</label>
              <div class="relative">
                <span class="absolute left-3 top-3 text-gray-400">
                  <Icon icon="mdi:email" class="w-4 h-4 text-primary" />
                </span>
                <input v-model="form.email" type="email" placeholder="Enter your email"
                  class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-500"
                  required />
              </div>
            </div>

            <div class="col-span-1">
              <label class="block text-sm font-medium text-gray-700 mb-1">Phone</label>
              <div class="relative">
                <span class="absolute left-3 top-3 text-gray-400">
                  <Icon icon="mdi:phone" class="w-4 h-4 text-primary" />
                </span>
                <input v-model="form.phone" type="text" placeholder="Enter your phone"
                  class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-500" />
              </div>
            </div>

            <div class="col-span-1">
              <label class="block text-sm font-medium text-gray-700 mb-1">Subject</label>
              <div class="relative">
                <span class="absolute left-3 top-3 text-gray-400">
                  <Icon icon="mdi:message-text" class="w-4 h-4 text-primary" />
                </span>
                <input v-model="form.subject" type="text" placeholder="Enter subject"
                  class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-500" />
              </div>
            </div>

            <div class="col-span-1 md:col-span-2">
              <label class="block text-sm font-medium text-gray-700 mb-1">Message</label>
              <div class="relative">
                <span class="absolute left-3 top-3 text-gray-400">
                  <Icon icon="mdi:note-text" class="w-4 h-4 text-primary" />
                </span>
                <textarea v-model="form.message" rows="4" placeholder="Write your message"
                  class="w-full pl-10 pr-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-primary focus:border-primary outline-none placeholder-gray-400 text-gray-500"></textarea>
              </div>
            </div>

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