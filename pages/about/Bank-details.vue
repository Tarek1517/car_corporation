<script setup>
import { Icon } from "@iconify/vue";

const bankInfo = {
  bankName: "Dhaka Bank Ltd.",
  branch: "Banasree Branch, Dhaka",
  accountNumber: "1234567890",
  swiftCode: "ABCDBDDH",
  iban: "BD12ABCD12345678901234",
  phone: "+880-2-9123456",
  email: "support@abcbank.com",
  workingHours: "Sun - Thu: 9:00 AM - 5:00 PM",
  departments: [
    { name: "Customer Service", email: "customerservice@abcbank.com" },
    { name: "Loans Department", email: "loans@abcbank.com" },
    { name: "Corporate Banking", email: "corporate@abcbank.com" },
  ],
};

const paymentMethods = [
  { name: "Visa", image: "/images/visa.png" },
  { name: "MasterCard", image: "/images/mastercard.png" },
  { name: "bKash", image: "/images/bkash1.png" },
  { name: "Nagad", image: "/images/nagad.jpg" },
  { name: "Rocket", image: "/images/rocket.png" },
];
</script>

<template>
  <section class="w-full relative overflow-hidden bg-gradient-to-br from-slate-50 via-white to-slate-100">
    <div class="absolute top-0 right-0 w-96 h-96 bg-primary/10 rounded-full -translate-y-1/3 translate-x-1/3 blur-3xl animate-pulse-slow"></div>
    <div class="absolute bottom-0 left-0 w-[32rem] h-[32rem] bg-secondary/10 rounded-full translate-y-1/3 -translate-x-1/3 blur-3xl animate-pulse-slow delay-1000"></div>
    <div class="absolute top-1/2 left-1/4 w-64 h-64 bg-primary/5 rounded-full blur-3xl animate-pulse-slow delay-500"></div>
    <div class="absolute inset-0 opacity-[0.03] bg-grid-pattern"></div>

    <section class="py-20">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
          <div class="bg-white p-8 rounded-3xl shadow-xl border border-gray-100 hover:shadow-2xl transition-all duration-300">
            <h2 class="text-3xl font-bold text-gray-900 mb-6">{{ bankInfo.bankName }}</h2>

            <div class="space-y-4 text-gray-700">
              <div class="flex items-center gap-4">
                <Icon icon="mdi:map-marker-outline" class="w-6 h-6 text-primary flex-shrink-0" />
                <span class="font-medium">{{ bankInfo.branch }}</span>
              </div>

              <div class="flex items-center gap-4">
                <Icon icon="mdi:bank-outline" class="w-6 h-6 text-primary flex-shrink-0" />
                <span>Account No: <strong>{{ bankInfo.accountNumber }}</strong></span>
              </div>

              <div class="flex items-center gap-4">
                <Icon icon="mdi:code-tags" class="w-6 h-6 text-primary flex-shrink-0" />
                <span>SWIFT: <strong>{{ bankInfo.swiftCode }}</strong></span>
              </div>

              <div class="flex items-center gap-4">
                <Icon icon="mdi:alpha-b-circle-outline" class="w-6 h-6 text-primary flex-shrink-0" />
                <span>IBAN: <strong>{{ bankInfo.iban }}</strong></span>
              </div>

              <div class="flex items-center gap-4">
                <Icon icon="mdi:phone-outline" class="w-6 h-6 text-primary flex-shrink-0" />
                <span>{{ bankInfo.phone }}</span>
              </div>

              <div class="flex items-center gap-4">
                <Icon icon="mdi:email-outline" class="w-6 h-6 text-primary flex-shrink-0" />
                <a :href="'mailto:' + bankInfo.email" class="hover:text-primary font-medium">{{ bankInfo.email }}</a>
              </div>

              <div class="flex items-center gap-4">
                <Icon icon="mdi:clock-time-four-outline" class="w-6 h-6 text-primary flex-shrink-0" />
                <span>{{ bankInfo.workingHours }}</span>
              </div>
            </div>

            <div class="mt-8 pt-6 border-t border-gray-200">
              <h3 class="text-xl font-semibold text-gray-800 mb-4">Department Contacts</h3>
              <div class="space-y-3">
                <div v-for="dept in bankInfo.departments" :key="dept.name" class="flex items-center justify-between text-sm">
                  <span class="font-medium">{{ dept.name }}:</span>
                  <a :href="'mailto:' + dept.email" class="text-gray-600 hover:text-primary">{{ dept.email }}</a>
                </div>
              </div>
            </div>
          </div>
          <div class="rounded-3xl overflow-hidden shadow-2xl h-full hover:scale-105 transition-transform duration-500">
            <img src="/images/bank-logo.jpg" class="w-full h-full object-cover border-0" loading="lazy" alt="Bank Logo">
          </div>
        </div>
      </div>
    </section>

    <div class="max-w-6xl mx-auto bg-white rounded-3xl shadow-xl p-8 md:p-12 border border-gray-100 hover:shadow-2xl transition-all duration-300 mt-12">
      <h3 class="text-center text-2xl font-semibold text-gray-800 mb-8">Secure Payment Options</h3>

      <div class="flex flex-wrap justify-center gap-6 mb-8">
        <div v-for="method in paymentMethods" :key="method.name" class="flex flex-col items-center bg-gray-50 p-4 rounded-xl hover:bg-gray-100 transition-colors duration-300">
          <img :src="method.image" :alt="method.name" class="w-24 h-24 object-contain" />
          <span class="mt-2 text-sm text-gray-600 font-medium">{{ method.name }}</span>
        </div>
      </div>

      <div class="flex items-center justify-center gap-2 mb-4">
        <Icon icon="mdi:lock-outline" class="text-green-500 w-5 h-5" />
        <span class="text-green-600 font-medium">Secure 256-bit SSL encryption</span>
      </div>

      <p class="text-center text-gray-600">
        We accept all major payment methods. Your transactions are fully secured and encrypted.
      </p>
    </div>
  </section>
</template>
