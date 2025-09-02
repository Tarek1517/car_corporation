<template>
  <footer class="bg-gray-900 text-gray-300 pt-16 pb-10 mt-20">
    <div class="container mx-auto px-6 lg:px-12">
      <!-- Top Section -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-12 mb-12">
        <!-- Brand & About -->
        <div>
          <NuxtLink to="/" class="flex items-center gap-2 mb-6">
            <img
              src="/images/logo.jpg"
              alt="ShopEase"
              class="h-12 rounded-lg"
            />
          </NuxtLink>
          <p class="text-gray-400 mb-6 leading-relaxed">
            Transforming the way you shop with quality products, seamless
            experience, and customer satisfaction.
          </p>
          <div class="flex gap-4">
            <a href="#"
              ><Icon name="logos:facebook" class="text-2xl hover:text-primary"
            /></a>
            <a href="#"
              ><Icon
                name="skill-icons:instagram"
                class="text-2xl hover:text-primary"
            /></a>
            <a href="#"
              ><Icon
                name="logos:youtube-icon"
                class="text-2xl hover:text-primary"
            /></a>
            <a href="#"
              ><Icon
                name="devicon:linkedin"
                class="text-2xl hover:text-primary"
            /></a>
          </div>
        </div>

        <!-- Quick Links -->
        <div class="grid grid-cols-2 gap-8">
          <div>
            <h3 class="text-white font-semibold text-lg mb-5">Company</h3>
            <ul class="space-y-3">
              <li>
                <NuxtLink to="/about" class="hover:text-primary"
                  >About Us</NuxtLink
                >
              </li>
              <li>
                <NuxtLink to="/Extra/AppDownload" class="hover:text-primary"
                  >App Download</NuxtLink
                >
              </li>
              <li>
                <NuxtLink to="/careers" class="hover:text-primary"
                  >Careers</NuxtLink
                >
              </li>
              <li>
                <NuxtLink to="/contact" class="hover:text-primary"
                  >Contact</NuxtLink
                >
              </li>
              <li>
                <NuxtLink to="/blog" class="hover:text-primary">Blog</NuxtLink>
              </li>
            </ul>
          </div>

          <div>
            <h3 class="text-white font-semibold text-lg mb-5">Support</h3>
            <ul class="space-y-3">
              <li>
                <NuxtLink to="/faq" class="hover:text-primary">FAQs</NuxtLink>
              </li>
              <li>
                <NuxtLink to="/shipping" class="hover:text-primary"
                  >Shipping</NuxtLink
                >
              </li>
              <li>
                <NuxtLink to="/returns" class="hover:text-primary"
                  >Returns</NuxtLink
                >
              </li>
              <li>
                <NuxtLink to="/tracking" class="hover:text-primary"
                  >Order Tracking</NuxtLink
                >
              </li>
            </ul>
          </div>
        </div>

        <!-- Policies & Newsletter -->
        <div>
          <h3 class="text-white font-semibold text-lg mb-5">Policies</h3>
          <ul class="space-y-3 mb-8">
            <li>
              <NuxtLink to="/terms" class="hover:text-primary"
                >Terms of Service</NuxtLink
              >
            </li>
            <li>
              <NuxtLink to="/privacy" class="hover:text-primary"
                >Privacy Policy</NuxtLink
              >
            </li>
            <li>
              <NuxtLink to="/seller-terms" class="hover:text-primary"
                >Seller Terms</NuxtLink
              >
            </li>
          </ul>

          <!-- Newsletter -->
          <h4 class="text-white font-medium mb-3">
            Subscribe to our newsletter
          </h4>
          <div class="flex gap-2">
            <input
              type="email"
              placeholder="Your email"
              class="bg-gray-800 border border-gray-700 rounded-lg px-4 py-2 text-sm text-gray-200 placeholder-gray-500 focus:ring-2 focus:ring-primary flex-grow"
            />
            <button
              class="bg-primary hover:bg-primary-dark text-white px-4 py-2 rounded-lg text-sm font-medium transition"
            >
              Subscribe
            </button>
          </div>
        </div>
      </div>

      <!-- Divider -->
      <div class="border-t border-gray-700 my-8"></div>

      <!-- Bottom Section -->
      <div class="flex flex-col md:flex-row justify-between items-center gap-6">
        <!-- Copy -->
        <p class="text-gray-500 text-sm text-center md:text-left">
          &copy; 2025 CarCorporationBD. All rights reserved.
        </p>

        <!-- App Download & Payment -->
        <div class="flex flex-col sm:flex-row items-center gap-6">
          <!-- App Badges -->
          <div class="flex gap-3">
            <a href="#" class="bg-black p-2 rounded-lg hover:opacity-90">
              <img
                src="https://upload.wikimedia.org/wikipedia/commons/7/78/Google_Play_Store_badge_EN.svg"
                alt="Play Store"
                class="h-8"
              />
            </a>
            <a href="#" class="bg-black p-2 rounded-lg hover:opacity-90">
              <img
                src="https://developer.apple.com/assets/elements/badges/download-on-the-app-store.svg"
                alt="App Store"
                class="h-8"
              />
            </a>
          </div>

          <!-- Payment Icons -->
          <div class="flex gap-3">
            <span class="text-gray-500 text-sm">
              Developed by
              <a
                href="https://creativetechpark.com/"
                target="_blank"
                rel="noopener noreferrer"
                class="text-primary hover:text-primary-dark transition-colors duration-300"
              >
                Creative Tech Park
              </a>
            </span>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
// No script needed
</script>

<style scoped>
/* Smooth transitions for all interactive elements */
a,
button,
input {
  transition: all 0.2s ease;
}

/* Custom focus styles */
input:focus,
button:focus {
  outline: none;
  box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.3);
}
</style>

<style scoped>
/* Smooth transitions for all interactive elements */
a,
button,
input {
  transition: all 0.2s ease;
}

/* Custom focus styles */
input:focus,
button:focus {
  outline: none;
  box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.3);
}
</style>
