<script setup lang="ts">
const founderMessage = `
Dear Valued Customers,

It is with great pleasure that I welcome you to Car Corporation Bangladesh. As the founder, I am proud to share our journey and our unwavering commitment to excellence in the automotive industry.

Since our inception, we have worked tirelessly to deliver trusted vehicles at competitive prices, ensuring that customer satisfaction remains our number one priority. Every car we import is carefully inspected to guarantee quality, reliability, and peace of mind.

Our mission is built on transparency, integrity, and long-lasting relationships. Whether you’re searching for a brand-new model, a pre-owned vehicle, or auction support, we are here to guide you every step of the way.

Thank you for trusting Car Corporation Bangladesh. Together, let us drive towards a brighter future in the automotive world.
`;

const founderAdvice = `
Success in business, as in life, is built on patience, hard work, and integrity. I encourage every customer and partner to dream big, act with honesty, and never give up when faced with challenges.

At Car Corporation Bangladesh, our vision goes beyond selling vehicles — we aim to build a culture of trust, growth, and service excellence for generations to come.
`;
</script>

<template>
  <section
    class="w-full relative overflow-hidden py-12 md:py-20 bg-gradient-to-br from-slate-50 via-white to-slate-100"
  >
    <div
      class="absolute top-0 right-0 w-96 h-96 bg-primary/10 rounded-full -translate-y-1/3 translate-x-1/3 blur-3xl animate-pulse-slow"
    ></div>
    <div
      class="absolute bottom-0 left-0 w-[32rem] h-[32rem] bg-secondary/10 rounded-full translate-y-1/3 -translate-x-1/3 blur-3xl animate-pulse-slow delay-1000"
    ></div>
    <div class="absolute inset-0 opacity-[0.04] bg-grid-pattern"></div>

    <div class="relative z-10 container mx-auto px-4 lg:px-8">
      <div class="flex flex-col lg:flex-row items-center gap-12 mb-20">
        <div
          class="lg:w-1/3 flex justify-center"
        >
          <img
            src="/images/avater1.png"
            alt="Founder of Car Corporation Bangladesh"
            class="shadow-xl w-full h-full object-cover rounded-2xl border-4 border-white"
          />
        </div>
        <div
          class="lg:w-2/3 space-y-6"
        >
          <div class="text-center lg:text-left">
            <h1 class="text-4xl font-bold text-gray-800 mb-2">
              A Personal Message From Our Founder
            </h1>
            <p class="text-xl text-gray-600">
              Sharing Our Journey & Commitment to Excellence
            </p>
          </div>

          <div
            class="bg-white/80 backdrop-blur-sm p-8 rounded-2xl shadow-lg leading-relaxed"
          >
            <p
              v-for="(para, i) in founderMessage.split('\n').filter(Boolean)"
              :key="i"
              class="text-gray-700 mb-4 text-lg"
            >
              {{ para }}
            </p>

            <div class="mt-6 pt-6 border-t border-gray-200 text-right">
              <p class="font-semibold text-primary text-lg">
                — [Founder Name]
              </p>
              <p class="text-gray-500 text-sm">
                Founder & CEO, Car Corporation Bangladesh
              </p>
            </div>
          </div>
        </div>
      </div>

      <div class="flex flex-col lg:flex-row-reverse items-center gap-12">
        <div
          class="lg:w-1/3 flex justify-center"
        >
          <img
            src="/images/avater2.png"
            alt="Founder"
            class="shadow-xl w-full h-full object-cover rounded-2xl border-4 border-white"
          />
        </div>
        <div
          class="lg:w-2/3 space-y-6"
          data-aos="fade-right"
          data-aos-delay="400"
        >
          <div class="text-center lg:text-left">
            <h1 class="text-4xl font-bold text-gray-800 mb-2">
              Advice from Our Founder
            </h1>
            <p class="text-xl text-gray-600">
              Continuing Our Vision & Strategic Direction
            </p>
          </div>

          <div
            class="bg-white/80 backdrop-blur-sm p-8 rounded-2xl shadow-lg leading-relaxed"
          >
            <blockquote
              v-for="(para, i) in founderAdvice.split('\n').filter(Boolean)"
              :key="i"
              class="text-gray-700 mb-4 text-lg italic border-l-4 border-primary pl-4"
            >
              {{ para }}
            </blockquote>

            <div class="mt-6 pt-6 border-t border-gray-200 text-right">
              <p class="text-sm text-gray-500 italic">
                "Success is not final, failure is not fatal: it is the courage
                to continue that counts."
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
