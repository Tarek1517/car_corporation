<script setup lang="ts">
// Animation logic could be added here if needed
</script>

<template>
  <section
    class="w-full relative overflow-hidden py-20 bg-gradient-to-br from-slate-50 via-white to-slate-100"
  >
    <div class="container mx-auto px-4 md:px-6 relative z-10">
      <!-- Background decorative elements -->
      <div
        class="absolute -top-24 -right-24 w-96 h-96 bg-primary/5 rounded-full blur-3xl"
      ></div>
      <div
        class="absolute -bottom-24 -left-24 w-80 h-80 bg-secondary/5 rounded-full blur-3xl"
      ></div>

      <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
        <!-- Content Section - Left Column -->
        <div class="flex flex-col justify-center items-start">
          <h2
            class="text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 leading-tight mb-6"
          >
            Download Our <br />
            <span
              class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary lg:text-7xl"
              >CarCorporationBD</span
            >
            Application
          </h2>
          <p class="text-gray-600 text-lg leading-relaxed max-w-xl">
            Direct access to global auctions with seamless import processes and
            premium vehicle selection with mobile app.
          </p>

          <div class="my-8">
            <ul class="list-disc space-y-2 text-gray-900 font-semibold">
              <li class="flex items-start">
                <Icon
                  name="mdi:checkbox-multiple-marked-circle"
                  class="w-5 h-5 mr-2 mt-1 flex-shrink-0 text-primary"
                />
                <span>User-Friendly Mobile Interface</span>
              </li>
              <li class="flex items-start">
                <Icon
                  name="mdi:checkbox-multiple-marked-circle"
                  class="w-5 h-5 mr-2 mt-1 flex-shrink-0 text-primary"
                />
                <span>Real-Time Auction Notifications</span>
              </li>
              <li class="flex items-start">
                <Icon
                  name="mdi:checkbox-multiple-marked-circle"
                  class="w-5 h-5 mr-2 mt-1 flex-shrink-0 text-primary"
                />
                <span>Secure In-App Payments</span>
              </li>
              <li class="flex items-start">
                <Icon
                  name="mdi:checkbox-multiple-marked-circle"
                  class="w-5 h-5 mr-2 mt-1 flex-shrink-0 text-primary"
                />
                <span>Personalized Car Recommendations</span>
              </li>
            </ul>
          </div>

          <div class="flex flex-col sm:flex-row gap-4 mt-6">
            <a
              href="#"
              class="inline-flex items-center justify-center space-x-3 px-6 py-3 bg-gradient-to-r from-primary to-secondary text-white rounded-xl font-medium shadow-lg hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1"
            >
              <Icon name="mdi:apple" class="text-2xl" />
              <div class="flex flex-col items-start">
                <p class="text-xs">Download on the</p>
                <p class="text-lg font-semibold">App Store</p>
              </div>
            </a>

            <a
              href="#"
              class="inline-flex items-center justify-center space-x-3 px-6 py-3 bg-gray-900 text-white rounded-xl font-medium shadow-lg hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1"
            >
              <Icon name="mdi:google-play" class="text-2xl" />
              <div class="flex flex-col items-start">
                <p class="text-xs">GET IT ON</p>
                <p class="text-lg font-semibold">Google Play</p>
              </div>
            </a>
          </div>
        </div>

        <!-- App Showcase Section - Right Column -->
        <div class="relative flex justify-center items-center">
          <div class="relative w-full max-w-md perspective-1000">
            <!-- Floating container with shadow -->
            <div
              class="absolute inset-0 bg-gradient-to-br from-primary/20 to-secondary/20 rounded-[3rem] blur-xl -z-10 transform rotate-3 animate-float"
            ></div>

            <!-- Back Device Frame -->
            <div
              class="absolute w-64 md:w-72 h-[28rem] md:h-[32rem] rounded-[2.5rem] border-[12px] border-gray-800 bg-gray-800 shadow-2xl left-8 md:left-16 -rotate-6 transform-style-preserve-3d"
            >
              <!-- Device notch -->
              <div
                class="absolute top-0 left-1/2 transform -translate-x-1/2 w-32 h-5 bg-gray-800 rounded-b-lg z-20"
              ></div>
              <!-- Screen content -->
              <div
                class="absolute inset-0 bg-gradient-to-br from-purple-400 to-blue-500 rounded-[2rem] overflow-hidden mt-2 mx-1 mb-3 p-5"
              >
                <!-- App UI elements -->
                <div class="flex justify-between items-center mb-8">
                  <div class="w-10 h-10 bg-white/30 rounded-full"></div>
                  <div class="w-20 h-6 bg-white/30 rounded-full"></div>
                </div>
                <div class="bg-white/30 rounded-2xl p-4 mb-4">
                  <div class="h-4 bg-white/50 rounded-full mb-2 w-3/4"></div>
                  <div class="h-4 bg-white/50 rounded-full w-1/2"></div>
                </div>
                <div class="grid grid-cols-2 gap-4 mb-6">
                  <div class="h-20 bg-white/30 rounded-xl"></div>
                  <div class="h-20 bg-white/30 rounded-xl"></div>
                </div>
                <div class="h-12 bg-white/30 rounded-full"></div>
              </div>
            </div>

            <!-- Front Device Frame -->
            <div
              class="relative w-64 md:w-72 h-[24rem] md:h-[28rem] rounded-[2.5rem] border-[12px] border-gray-800 bg-gray-800 shadow-2xl left-16 md:left-32 transform-style-preserve-3d animate-float"
            >
              <!-- Device notch -->
              <div
                class="absolute top-0 left-1/2 transform -translate-x-1/2 w-32 h-5 bg-gray-800 rounded-b-lg z-20"
              ></div>
              <!-- Screen content -->
              <div
                class="absolute inset-0 bg-gradient-to-br from-primary to-secondary rounded-[2rem] overflow-hidden mt-2 mx-1 mb-3 p-5"
              >
                <!-- App UI elements -->
                <div class="flex justify-between items-center mb-6">
                  <div class="text-white font-bold text-lg">
                    CarCorporationBD
                  </div>
                  <div class="w-6 h-6 bg-white/30 rounded-full"></div>
                </div>
                <div class="text-center mb-8">
                  <div
                    class="w-16 h-16 bg-white/30 rounded-full mx-auto mb-4"
                  ></div>
                  <div
                    class="h-4 bg-white/30 rounded-full mx-auto w-3/4 mb-2"
                  ></div>
                  <div class="h-3 bg-white/20 rounded-full mx-auto w-1/2"></div>
                </div>
                <div class="space-y-3">
                  <div class="h-10 bg-white/30 rounded-full"></div>
                  <div class="h-10 bg-white/30 rounded-full"></div>
                </div>
                <div
                  class="absolute bottom-5 left-5 right-5 flex justify-between"
                >
                  <div class="w-10 h-10 bg-white/30 rounded-full"></div>
                  <div class="w-10 h-10 bg-white/30 rounded-full"></div>
                  <div class="w-10 h-10 bg-white/30 rounded-full"></div>
                  <div class="w-10 h-10 bg-white/30 rounded-full"></div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style>
.transform-style-preserve-3d {
  transform-style: preserve-3d;
}
.animate-float {
  animation: float 6s ease-in-out infinite;
}
@keyframes float {
  0%,
  100% {
    transform: translateY(0) rotate(0deg);
  }
  50% {
    transform: translateY(-20px) rotate(2deg);
  }
}
</style>
