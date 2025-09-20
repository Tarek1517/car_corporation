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

const companyValues = [
  {
    title: "Integrity",
    description: "We conduct business with honesty and transparency in all our dealings.",
    icon: "🤝"
  },
  {
    title: "Quality",
    description: "Every vehicle undergoes rigorous inspection to ensure highest standards.",
    icon: "✅"
  },
  {
    title: "Customer Focus",
    description: "Your satisfaction is our top priority in every interaction.",
    icon: "👥"
  },
  {
    title: "Innovation",
    description: "We continuously improve our processes to serve you better.",
    icon: "💡"
  }
];

const journeyHighlights = [
  {
    year: "2010",
    title: "Company Founded",
    description: "Started with a vision to revolutionize car buying in Bangladesh"
  },
  {
    year: "2015",
    title: "Expansion",
    description: "Opened showrooms in 5 major cities across the country"
  },
  {
    year: "2020",
    title: "Digital Transformation",
    description: "Launched online platform for seamless vehicle browsing and purchasing"
  },
  {
    year: "2023",
    title: "Industry Leader",
    description: "Recognized as the top automotive importer in Bangladesh"
  }
];
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
      <div class="text-center mb-16">
        <h1 class="text-4xl md:text-5xl font-bold text-gray-800 mb-4">
          Our Story & Vision
        </h1>
        <p class="text-xl text-gray-600 max-w-3xl mx-auto">
          Learn about our journey, values, and the people behind Car Corporation Bangladesh
        </p>
      </div>
      <div class="flex flex-col lg:flex-row items-center gap-12 mb-20">
        <div
          class="lg:w-1/3 flex justify-center"
        >
          <div class="relative">
            <img
              src="/images/avater1.png"
              alt="Founder of Car Corporation Bangladesh"
              class="shadow-xl w-64 h-64 object-cover rounded-2xl border-4 border-white"
            />
            <div class="absolute -bottom-4 -right-4 bg-primary text-white py-2 px-4 rounded-lg shadow-lg">
              <span class="font-semibold">Since 2010</span>
            </div>
          </div>
        </div>
        <div
          class="lg:w-2/3 space-y-6"
        >
          <div class="text-center lg:text-left">
            <h2 class="text-3xl font-bold text-gray-800 mb-2">
              A Personal Message From Our Founder
            </h2>
            <p class="text-lg text-gray-600">
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
      <div class="mb-20">
        <div class="text-center mb-12">
          <h2 class="text-3xl font-bold text-gray-800 mb-4">Our Core Values</h2>
          <p class="text-lg text-gray-600 max-w-2xl mx-auto">
            The principles that guide every decision we make at Car Corporation Bangladesh
          </p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
          <div 
            v-for="(value, index) in companyValues" 
            :key="index"
            class="bg-white/80 backdrop-blur-sm p-6 rounded-2xl shadow-lg text-center hover:shadow-xl transition-shadow duration-300"
          >
            <div class="text-4xl mb-4">{{ value.icon }}</div>
            <h3 class="text-xl font-bold text-gray-800 mb-2">{{ value.title }}</h3>
            <p class="text-gray-600">{{ value.description }}</p>
          </div>
        </div>
      </div>
      <div class="mb-20">
        <div class="text-center mb-12">
          <h2 class="text-3xl font-bold text-gray-800 mb-4">Our Journey</h2>
          <p class="text-lg text-gray-600 max-w-2xl mx-auto">
            Key milestones in our history of serving Bangladesh's automotive needs
          </p>
        </div>

        <div class="relative">
          <div class="absolute left-1/2 transform -translate-x-1/2 h-full w-1 bg-primary/20"></div>
          
          <div 
            v-for="(milestone, index) in journeyHighlights" 
            :key="index"
            class="mb-12 flex flex-col md:flex-row items-center"
            :class="{ 'md:flex-row-reverse': index % 2 !== 0 }"
          >
            <div class="md:w-1/2 mb-6 md:mb-0 md:px-8">
              <div class="bg-white/80 backdrop-blur-sm p-6 rounded-2xl shadow-lg">
                <div class="text-primary font-bold text-lg mb-2">{{ milestone.year }}</div>
                <h3 class="text-xl font-bold text-gray-800 mb-2">{{ milestone.title }}</h3>
                <p class="text-gray-600">{{ milestone.description }}</p>
              </div>
            </div>
            
            <div class="md:w-0 flex justify-center">
              <div class="w-8 h-8 rounded-full bg-primary border-4 border-white z-10"></div>
            </div>
            
            <div class="md:w-1/2 hidden md:block"></div>
          </div>
        </div>
      </div>
      <div class="flex flex-col lg:flex-row-reverse items-center gap-12 mb-20">
        <div
          class="lg:w-1/3 flex justify-center"
        >
          <div class="relative">
            <img
              src="/images/avater2.png"
              alt="Founder"
              class="shadow-xl w-64 h-64 object-cover rounded-2xl border-4 border-white"
            />
            <div class="absolute -bottom-4 -left-4 bg-secondary text-white py-2 px-4 rounded-lg shadow-lg">
              <span class="font-semibold">Leadership</span>
            </div>
          </div>
        </div>
        <div
          class="lg:w-2/3 space-y-6"
          data-aos="fade-right"
          data-aos-delay="400"
        >
          <div class="text-center lg:text-left">
            <h2 class="text-3xl font-bold text-gray-800 mb-2">
              Advice from Our Founder
            </h2>
            <p class="text-lg text-gray-600">
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