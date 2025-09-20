<template>
  <div class="w-full relative">
    <header>
      <MobileHeader/>
      <Header />
    </header>

    <main class="pt-16 lg:pt-0">
      <slot />
      <div
        class="fixed top-1/2 right-4 z-50 flex flex-col space-y-4 transform -translate-y-1/2 transition-all duration-500"
      >
        <div
          class="relative group cursor-pointer"
          title="24/7 Roadside Assistance"
        >
          <div
            class="w-8 h-8 bg-gradient-to-r from-red-600 to-red-700 rotate-45 transform origin-center shadow-lg transition-all duration-300 transform group-hover:scale-110 group-hover:shadow-xl hover:animate-pulse"
          >
            <div class="w-8 h-8 bg-white/10 rounded-full flex items-center justify-center -rotate-45">
              <Icon
                name="mdi:car-repair"
                class="text-white w-8 h-8"
              />
            </div>
          </div>
          <div class="absolute right-16 top-1/2 transform -translate-y-1/2 opacity-0 group-hover:opacity-100 transition-all duration-500 ease-out pointer-events-none whitespace-nowrap">
            <div class="bg-gradient-to-r from-red-600 to-red-700 text-white text-sm px-4 py-2 rounded-lg shadow-xl flex items-center overflow-hidden">
              <span class="relative z-10 text-xl font-medium transform translate-x-4 group-hover:translate-x-0 transition-transform duration-500 ease-out delay-100">24/7 Roadside Assistance</span>
              <div class="absolute inset-0 bg-gradient-to-r from-red-700 to-red-800 transform -translate-x-full group-hover:translate-x-0 transition-transform duration-500 ease-out"></div>
              <div class="absolute -right-2 top-1/2 transform -translate-y-1/2 w-0 h-0 border-t-8 border-t-transparent border-b-8 border-b-transparent border-l-8 border-l-red-700"></div>
            </div>
          </div>
        </div>
        
        <div class="relative group cursor-pointer">
          <div
            class="w-8 h-8 bg-gradient-to-r from-red-600 to-red-700 rotate-45 transform origin-center shadow-lg transition-all duration-300 transform group-hover:scale-110 group-hover:shadow-xl hover:animate-pulse"
          >
            <div class="w-8 h-8 bg-white/10 rounded-full flex items-center justify-center -rotate-45">
              <Icon
                name="mdi:steering"
                class="text-white w-8 h-8"
              />
            </div>
          </div>
          
          <div class="absolute right-16 top-1/2 transform -translate-y-1/2 opacity-0 group-hover:opacity-100 transition-all duration-500 ease-out pointer-events-none whitespace-nowrap">
            <div class="bg-gradient-to-r from-red-600 to-red-700 text-white text-sm px-4 py-2 rounded-lg shadow-xl flex items-center overflow-hidden">
              <span class="relative z-10 text-xl font-medium transform translate-x-4 group-hover:translate-x-0 transition-transform duration-500 ease-out delay-100">Customer Service</span>
              <div class="absolute inset-0 bg-gradient-to-r from-red-700 to-red-800 transform -translate-x-full group-hover:translate-x-0 transition-transform duration-500 ease-out"></div>
              <div class="absolute -right-2 top-1/2 transform -translate-y-1/2 w-0 h-0 border-t-8 border-t-transparent border-b-8 border-b-transparent border-l-8 border-l-red-700"></div>
            </div>
          </div>
        </div>
        
        <div class="relative group cursor-pointer">
          <div
            class="w-8 h-8 bg-gradient-to-r from-red-600 to-red-700 rotate-45 transform origin-center shadow-lg transition-all duration-300 transform group-hover:scale-110 group-hover:shadow-xl hover:animate-pulse"
          >
            <div class="w-8 h-8 bg-white/10 rounded-full flex items-center justify-center -rotate-45">
              <Icon
                name="material-symbols:receipt-long"
                class="text-white w-8 h-8"
              />
            </div>
          </div>
          
          <div class="absolute right-16 top-1/2 transform -translate-y-1/2 opacity-0 group-hover:opacity-100 transition-all duration-500 ease-out pointer-events-none whitespace-nowrap">
            <div class="bg-gradient-to-r from-red-600 to-red-700 text-white text-sm px-4 py-2 rounded-lg shadow-xl flex items-center overflow-hidden">
              <span class="relative z-10 text-xl font-medium transform translate-x-4 group-hover:translate-x-0 transition-transform duration-500 ease-out delay-100">Help Center</span>
              <div class="absolute inset-0 bg-gradient-to-r from-red-700 to-red-800 transform -translate-x-full group-hover:translate-x-0 transition-transform duration-500 ease-out"></div>
              <div class="absolute -right-2 top-1/2 transform -translate-y-1/2 w-0 h-0 border-t-8 border-t-transparent border-b-8 border-b-transparent border-l-8 border-l-red-700"></div>
            </div>
          </div>
        </div>
      </div>
    </main>

    <footer>
      <Footer />
    </footer>
  </div>
</template>

<style scoped>
@keyframes pulse {
  0% {
    box-shadow: 0 0 0 0 rgba(239, 68, 68, 0.7);
  }
  70% {
    box-shadow: 0 0 0 10px rgba(239, 68, 68, 0);
  }
  100% {
    box-shadow: 0 0 0 0 rgba(239, 68, 68, 0);
  }
}

.animate-pulse {
  animation: pulse 2s infinite;
}

.tooltip-text {
  position: relative;
  z-index: 10;
}

.tooltip-bg {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(to right, #b91c1c, #991b1b);
  transform: translateX(-100%);
  transition: transform 0.5s ease-out;
}

.group:hover .tooltip-bg {
  transform: translateX(0);
}
</style>