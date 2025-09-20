<script setup lang="ts">
const coFounderMessage = `
Dear Friends and Partners,

It gives me immense pride to stand beside our Founder and lead Car Corporation Bangladesh towards a future of innovation, trust, and service excellence.

From day one, our mission has been to make the process of owning a car easier, more transparent, and more reliable for every customer. I personally ensure that our operations, inspections, and services run smoothly so you can enjoy a stress-free journey when choosing your vehicle.

At Car Corporation Bangladesh, we don’t just sell cars — we build relationships. Our team is committed to serving you with honesty, efficiency, and dedication at every step.

Thank you for placing your confidence in us. Together, let’s drive forward with strength and vision.
`;

const coFounderAdvice = `
To achieve lasting success, one must stay humble, focused, and consistent. Challenges will come, but they should be seen as opportunities to grow stronger.

At Car Corporation Bangladesh, our strategy is simple: serve customers with sincerity, maintain global standards, and always move forward with innovation. That is how we will continue to earn your trust and loyalty.
`;
</script>

<template>
  <section
    class="w-full relative overflow-hidden py-12 md:py-20 bg-gradient-to-br from-slate-50 via-white to-slate-100"
  >
    <!-- Background accents -->
    <div
      class="absolute top-0 right-0 w-96 h-96 bg-primary/10 rounded-full -translate-y-1/3 translate-x-1/3 blur-3xl animate-pulse-slow"
    ></div>
    <div
      class="absolute bottom-0 left-0 w-[32rem] h-[32rem] bg-secondary/10 rounded-full translate-y-1/3 -translate-x-1/3 blur-3xl animate-pulse-slow delay-1000"
    ></div>
    <div class="absolute inset-0 opacity-[0.04] bg-grid-pattern"></div>

    <div class="relative z-10 container mx-auto px-4 lg:px-8">
      <!-- Message from Co-Founder -->
      <div class="flex flex-col lg:flex-row items-center gap-12 mb-20">
        <div class="lg:w-1/3 flex justify-center">
          <img
            src="/images/avater2.png"
            alt="Co-Founder of Car Corporation Bangladesh"
            class="shadow-xl w-full h-full object-cover rounded-2xl border-4 border-white"
          />
        </div>
        <div class="lg:w-2/3 space-y-6">
          <div class="text-center lg:text-left">
            <h1 class="text-4xl font-bold text-gray-800 mb-2">
              A Message from Our Co-Founder
            </h1>
            <p class="text-xl text-gray-600">
              Supporting Our Vision & Driving Operations Forward
            </p>
          </div>

          <div
            class="bg-white/80 backdrop-blur-sm p-8 rounded-2xl shadow-lg leading-relaxed"
          >
            <p
              v-for="(para, i) in coFounderMessage.split('\n').filter(Boolean)"
              :key="i"
              class="text-gray-700 mb-4 text-lg"
            >
              {{ para }}
            </p>

            <div class="mt-6 pt-6 border-t border-gray-200 text-right">
              <p class="font-semibold text-secondary text-lg">
                — [Co-Founder Name]
              </p>
              <p class="text-gray-500 text-sm">
                Co-Founder & COO, Car Corporation Bangladesh
              </p>
            </div>
          </div>
        </div>
      </div>

      <div class="flex flex-col lg:flex-row-reverse items-center gap-12">
        <div class="lg:w-1/3 flex justify-center">
          <img
            src="/images/avater1.png"
            alt="Co-Founder"
            class="shadow-xl w-full h-full object-cover rounded-2xl border-4 border-white"
          />
        </div>
        <div class="lg:w-2/3 space-y-6">
          <div class="text-center lg:text-left">
            <h1 class="text-4xl font-bold text-gray-800 mb-2">
              Advice from Our Co-Founder
            </h1>
            <p class="text-xl text-gray-600">
              Guiding Principles for Growth & Success
            </p>
          </div>

          <div
            class="bg-white/80 backdrop-blur-sm p-8 rounded-2xl shadow-lg leading-relaxed"
          >
            <blockquote
              v-for="(para, i) in coFounderAdvice.split('\n').filter(Boolean)"
              :key="i"
              class="text-gray-700 mb-4 text-lg italic border-l-4 border-secondary pl-4"
            >
              {{ para }}
            </blockquote>

            <div class="mt-6 pt-6 border-t border-gray-200 text-right">
              <p class="text-sm text-gray-500 italic">
                "Leadership is not about being in charge, it’s about taking care
                of those in your charge."
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
