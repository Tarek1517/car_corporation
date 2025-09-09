<script setup>
</script>

<template>
  <section class="w-full relative overflow-hidden py-2 md:py-6 bg-gradient-to-br from-slate-50 via-white to-slate-100">
    <!-- Background blobs -->
    <div class="absolute top-0 right-0 w-96 h-96 bg-primary/10 rounded-full -translate-y-1/3 translate-x-1/3 blur-3xl animate-pulse-slow"></div>
    <div class="absolute bottom-0 left-0 w-[32rem] h-[32rem] bg-secondary/10 rounded-full translate-y-1/3 -translate-x-1/3 blur-3xl animate-pulse-slow delay-1000"></div>
    <div class="absolute top-1/2 left-1/4 w-64 h-64 bg-primary/5 rounded-full blur-3xl animate-pulse-slow delay-500"></div>
    <div class="absolute inset-0 opacity-[0.03] bg-grid-pattern"></div>

    <div class="relative z-10">
      <!-- Hero Section -->
      <div class="pb-12 relative">
        <div class="absolute top-0 left-0 w-64 h-64 bg-primary/5 rounded-full blur-3xl -translate-x-1/2 -translate-y-1/2"></div>
        <div class="absolute bottom-0 right-0 w-80 h-80 bg-secondary/5 rounded-full blur-3xl translate-x-1/3 translate-y-1/3"></div>

        <div class="relative z-10 text-center mb-16">
          <div class="relative h-[500px] md:h-[600px] w-full">
            <img src="../../public/images/herovison.jpg" alt="Car Financing Background" class="w-full h-full object-cover" />
            <div class="absolute inset-0 flex flex-col items-center justify-center text-center px-4 z-10">
              <h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-4">
                Our
                <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">
                  Financing
                </span>
                Solutions
              </h2>
              <p class="text-xl text-gray-100 max-w-2xl">
                Affordable car loans and flexible payment plans designed to make owning your dream car simple and stress-free.
              </p>
            </div>
          </div>

          <!-- Financing Cards -->
          <div class="relative -mt-30 z-20">
            <div class="max-w-7xl mx-auto px-4">
              <div class="bg-white rounded-3xl shadow-xl p-6 md:p-10 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 md:gap-8">
                <!-- Card 1 -->
                <div class="group text-start rounded-2xl p-4 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-primary/20 hover:-translate-y-2 relative overflow-hidden">
                  <div class="absolute top-0 right-0 w-20 h-20 bg-primary/5 rounded-bl-full transition-all duration-500 group-hover:bg-primary/10"></div>
                  <div class="flex justify-start mb-5 relative z-10">
                    <div class="p-3 bg-gradient-to-br from-primary/10 to-primary/5 rounded-xl transition-colors duration-500 group-hover:from-primary/15 group-hover:to-primary/10 shadow-sm">
                      <Icon name="mdi:cash-multiple" class="w-7 h-7 text-primary" />
                    </div>
                  </div>
                  <h3 class="font-semibold text-xl text-gray-900 mb-2 relative z-10">Flexible Loan Plans</h3>
                  <span class="text-primary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0 relative z-10">Choose a plan</span>
                </div>

                <!-- Card 2 -->
                <div class="group text-start rounded-2xl p-4 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-secondary/20 hover:-translate-y-2 relative overflow-hidden">
                  <div class="absolute top-0 right-0 w-20 h-20 bg-secondary/5 rounded-bl-full transition-all duration-500 group-hover:bg-secondary/10"></div>
                  <div class="flex justify-start mb-5 relative z-10">
                    <div class="p-3 bg-gradient-to-br from-secondary/10 to-secondary/5 rounded-xl transition-colors duration-500 group-hover:from-secondary/15 group-hover:to-secondary/10 shadow-sm">
                      <Icon name="mdi:bank" class="w-7 h-7 text-secondary" />
                    </div>
                  </div>
                  <h3 class="font-semibold text-xl text-gray-900 mb-2 relative z-10">Instant Approval</h3>
                  <span class="text-secondary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0 relative z-10">Get approved quickly</span>
                </div>

                <!-- Card 3 -->
                <div class="group text-start rounded-2xl p-4 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-primary/20 hover:-translate-y-2 relative overflow-hidden">
                  <div class="absolute top-0 right-0 w-20 h-20 bg-primary/5 rounded-bl-full transition-all duration-500 group-hover:bg-primary/10"></div>
                  <div class="flex justify-start mb-5 relative z-10">
                    <div class="p-3 bg-gradient-to-br from-primary/10 to-primary/5 rounded-xl transition-colors duration-500 group-hover:from-primary/15 group-hover:to-primary/10 shadow-sm">
                      <Icon name="mdi:car" class="w-7 h-7 text-primary" />
                    </div>
                  </div>
                  <h3 class="font-semibold text-xl text-gray-900 mb-2 relative z-10">Affordable Cars</h3>
                  <span class="text-primary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0 relative z-10">Select your car</span>
                </div>

                <!-- Card 4 -->
                <div class="group text-start rounded-2xl p-4 transition-all duration-500 hover:shadow-xl shadow-md border border-gray-100 hover:border-secondary/20 hover:-translate-y-2 relative overflow-hidden">
                  <div class="absolute top-0 right-0 w-20 h-20 bg-secondary/5 rounded-bl-full transition-all duration-500 group-hover:bg-secondary/10"></div>
                  <div class="flex justify-start mb-5 relative z-10">
                    <div class="p-3 bg-gradient-to-br from-secondary/10 to-secondary/5 rounded-xl transition-colors duration-500 group-hover:from-secondary/15 group-hover:to-secondary/10 shadow-sm">
                      <Icon name="mdi:shield-check" class="w-7 h-7 text-secondary" />
                    </div>
                  </div>
                  <h3 class="font-semibold text-xl text-gray-900 mb-2 relative z-10">Trusted Support</h3>
                  <span class="text-secondary text-sm font-medium transition-all duration-300 ml-3 group-hover:opacity-100 opacity-0 relative z-10">We assist you</span>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center mt-12">
          <div class="relative">
            <div class="rounded-2xl overflow-hidden shadow-xl border-4 border-white">
              <img src="../../public/images/vison1.jpg" alt="Our Journey" class="w-full h-full object-cover" />
            </div>
            <div class="absolute -bottom-6 -right-6 w-40 h-40 bg-gradient-to-r from-primary to-secondary rounded-2xl shadow-lg -z-10"></div>
          </div>

          <div>
            <div class="mb-4 flex items-center justify-center">
              <div class="h-0.5 w-8 bg-primary mr-3"></div>
              <span class="text-sm font-semibold tracking-wider text-primary uppercase">Financial Support</span>
              <div class="h-0.5 w-8 bg-primary ml-3"></div>
            </div>
            <p class="text-gray-600 text-lg max-w-3xl mx-auto">
              Helping clients finance and own cars easily with low-interest loans and customized payment options.
            </p>
            <h3 class="text-2xl font-bold text-gray-900 mb-6">Building Trust in Car Financing Since 2010</h3>
            <p class="text-gray-600 mb-6">
              Car Finance BD started with a vision to simplify car ownership for everyone. Today, we provide transparent, reliable, and quick financing solutions for all types of vehicles.
            </p>

            <div class="space-y-4 mb-8">
              <div class="flex items-start">
                <div class="bg-primary/10 p-2 rounded-lg mr-4 flex-shrink-0">
                  <Icon name="mdi:target" class="w-6 h-6 text-primary" />
                </div>
                <div>
                  <h4 class="font-semibold text-gray-900 mb-1">Ownership</h4>
                  <p class="text-gray-600 text-sm">
                    Make car ownership accessible through flexible loans and expert financial guidance.
                  </p>
                </div>
              </div>

              <div class="flex items-start">
                <div class="bg-secondary/10 p-2 rounded-lg mr-4 flex-shrink-0">
                  <Icon name="mdi:eye-outline" class="w-6 h-6 text-secondary" />
                </div>
                <div>
                  <h4 class="font-semibold text-gray-900 mb-1">Financing Support</h4>
                  <p class="text-gray-600 text-sm">
                    To be the most trusted car financing partner in Bangladesh.
                  </p>
                </div>
              </div>
            </div>

            <div class="flex gap-4">
              <div class="bg-gray-50 rounded-lg px-4 py-3">
                <div class="text-2xl font-bold text-primary">120K+</div>
                <div class="text-sm text-gray-500">Loans Approved</div>
              </div>
              <div class="bg-gray-50 rounded-lg px-4 py-3">
                <div class="text-2xl font-bold text-primary">10K+</div>
                <div class="text-sm text-gray-500">Satisfied Clients</div>
              </div>
            </div>

            <button class="mt-8 px-6 py-3 bg-gradient-to-r from-primary to-secondary text-white rounded-lg font-medium shadow-lg hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1 flex items-center">
              <span>Learn More</span>
              <Icon name="mdi:arrow-right" class="ml-2 w-5 h-5" />
            </button>
          </div>
        </div>
      </div>
    </div>
    <div class="">
        <HomeProductsSection/>
    </div>
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

.custom-bullet {
  display: inline-block;
  width: 10px;
  height: 10px;
  background-color: rgba(255, 255, 255, 0.6);
  border-radius: 50%;
  margin: 0 4px;
  cursor: pointer;
  transition: all 0.3s ease;
}

.custom-bullet-active {
  background-color: #fff;
  width: 24px;
  border-radius: 8px;
}

/* Smooth transitions for all elements */
* {
  transition-property: color, background-color, border-color, transform, box-shadow;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 300ms;
}
</style>
