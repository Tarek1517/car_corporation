<template>
  <section class="w-full bg-white text-gray-800 overflow-hidden">
    <div class="relative bg-gray-100 min-h-[70vh] flex items-center">
      <img src="/images/city-new-web.png" alt="Honda City" class="w-full h-full object-cover absolute inset-0" />
      <div class="absolute inset-0 bg-gradient-to-r from-black/70 to-black/30"></div>
      <div class="relative max-w-7xl mx-auto px-6 py-20 text-white z-10">
        <div class="max-w-2xl">
          <span class="inline-block px-3 py-1 bg-red-600 text-xs font-semibold rounded-full mb-4">NEW MODEL</span>
          <h1 class="text-4xl md:text-6xl font-bold mb-6 animate-fade-in">Honda City</h1>
          <p class="text-lg md:text-xl mb-8 max-w-xl animate-fade-in delay-150">
            Personal space is hard to come by these days but with room to move and room to breathe, the Honda City lets you rediscover space.
          </p>
          <div class="flex flex-wrap gap-4 mb-10 animate-fade-in delay-300">
            <div class="bg-red-800/90 px-5 py-3 rounded-lg flex items-center gap-2">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M10 9a3 3 0 100-6 3 3 0 000 6zm-7 9a7 7 0 1114 0H3z" clip-rule="evenodd" />
              </svg>
              Room for 4 adults
            </div>
            <div class="bg-red-800/90 px-5 py-3 rounded-lg flex items-center gap-2">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
                <path d="M2 4a1 1 0 011-1h2a1 1 0 011 1v12a1 1 0 01-1 1H3a1 1 0 01-1-1V4zM8 4a1 1 0 011-1h2a1 1 0 011 1v12a1 1 0 01-1 1H9a1 1 0 01-1-1V4zM15 3a1 1 0 00-1 1v12a1 1 0 001 1h2a1 1 0 001-1V4a1 1 0 00-1-1h-2z" />
              </svg>
              7-inch Touchscreen Audio
            </div>
          </div>
          <div class="flex flex-wrap gap-4 animate-fade-in delay-500">
            <button class="px-6 py-3 bg-red-600 hover:bg-red-700 text-white font-medium rounded-lg transition-all duration-300 transform hover:scale-105">
              Book a Test Drive
            </button>
            <button class="px-6 py-3 bg-transparent border-2 border-white hover:bg-white hover:text-gray-900 text-white font-medium rounded-lg transition-all duration-300">
              View Specifications
            </button>
          </div>
        </div>
      </div>
    </div>

    <section class="max-w-7xl mx-auto px-6 py-20">
      <div class="mb-16 text-center">
        <span class="inline-block px-3 py-1 bg-red-100 text-red-800 text-xs font-semibold rounded-full mb-4">DESIGN</span>
        <h2 class="text-3xl md:text-4xl font-bold mb-4 text-gray-900">Sleek & Modern Styling</h2>
        <p class="text-gray-600 max-w-2xl mx-auto">The City offers sleek styling with modern touches that make it stand out wherever you go.</p>
      </div>
      
      <div class="grid md:grid-cols-2 gap-12 items-center">
        <div class="relative group">
          <img src="/images/city-new-web.png" alt="Honda City Styling" class="rounded-xl shadow-xl w-full h-auto transform transition-transform duration-500 group-hover:scale-105" />
          <div class="absolute inset-0 bg-gradient-to-t from-black/50 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 rounded-xl"></div>
        </div>
        <div>
          <div class="space-y-6">
            <div class="flex items-start gap-4">
              <div class="mt-1 p-2 bg-red-100 rounded-lg">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-red-600" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                </svg>
              </div>
              <div>
                <h3 class="text-xl font-bold mb-2">Aerodynamic Design</h3>
                <p class="text-gray-600">Streamlined body reduces drag and improves fuel efficiency.</p>
              </div>
            </div>
            
            <div class="flex items-start gap-4">
              <div class="mt-1 p-2 bg-red-100 rounded-lg">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-red-600" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                </svg>
              </div>
              <div>
                <h3 class="text-xl font-bold mb-2">Premium Finish</h3>
                <p class="text-gray-600">High-quality paint and materials for a luxurious look and feel.</p>
              </div>
            </div>
            
            <div class="flex items-start gap-4">
              <div class="mt-1 p-2 bg-red-100 rounded-lg">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-red-600" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                </svg>
              </div>
              <div>
                <h3 class="text-xl font-bold mb-2">Distinctive Grille</h3>
                <p class="text-gray-600">Bold front grille design makes a strong first impression.</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="bg-gradient-to-br from-gray-50 to-gray-100 py-20">
      <div class="max-w-7xl mx-auto px-6">
        <div class="mb-16 text-center">
          <span class="inline-block px-3 py-1 bg-red-100 text-red-800 text-xs font-semibold rounded-full mb-4">INTERIOR</span>
          <h2 class="text-3xl md:text-4xl font-bold mb-4 text-gray-900">Space & Storage</h2>
          <p class="text-gray-600 max-w-2xl mx-auto">It’s amazing the little details you can accommodate inside. Ample storage compartments mean there’s a place for everything.</p>
        </div>
        
        <div class="grid md:grid-cols-2 gap-12 items-center">
          <div class="order-2 md:order-1">
            <div class="space-y-6">
              <div class="bg-white p-6 rounded-xl shadow-sm border border-gray-100">
                <h3 class="text-xl font-bold mb-3 flex items-center gap-2">
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-red-600" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20 7l-8-4-8 4m16 0l-8 4m8-4v10l-8 4m0-10L4 7m8 4v10M4 7v10l8 4" />
                  </svg>
                  Spacious Boot
                </h3>
                <p class="text-gray-600">Generous luggage space for all your travel needs with 510 liters of capacity.</p>
              </div>
              
              <div class="bg-white p-6 rounded-xl shadow-sm border border-gray-100">
                <h3 class="text-xl font-bold mb-3 flex items-center gap-2">
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-red-600" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2H6a2 2 0 01-2-2V6zM14 6a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2h-2a2 2 0 01-2-2V6zM4 16a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2H6a2 2 0 01-2-2v-2zM14 16a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2h-2a2 2 0 01-2-2v-2z" />
                  </svg>
                  Flexible Seating
                </h3>
                <p class="text-gray-600">60:40 split fold rear seats for versatile cargo and passenger configurations.</p>
              </div>
              
              <div class="bg-white p-6 rounded-xl shadow-sm border border-gray-100">
                <h3 class="text-xl font-bold mb-3 flex items-center gap-2">
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-red-600" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 11H5m14 0a2 2 0 012 2v6a2 2 0 01-2 2H5a2 2 0 01-2-2v-6a2 2 0 012-2m14 0V9a2 2 0 00-2-2M5 11V9a2 2 0 012-2m0 0V5a2 2 0 012-2h6a2 2 0 012 2v2M7 7h10" />
                  </svg>
                  Smart Storage
                </h3>
                <p class="text-gray-600">Thoughtfully designed compartments for bottles, devices, and personal items.</p>
              </div>
            </div>
          </div>
          
          <div class="order-1 md:order-2 relative group">
            <img src="/images/city-new-web.png" alt="Honda City Interior" class="rounded-xl shadow-xl w-full h-auto transform transition-transform duration-500 group-hover:scale-105" />
            <div class="absolute inset-0 bg-gradient-to-t from-black/50 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 rounded-xl"></div>
          </div>
        </div>
      </div>
    </section>
    <section class="max-w-7xl mx-auto px-6 py-20">
      <div class="mb-16 text-center">
        <span class="inline-block px-3 py-1 bg-red-100 text-red-800 text-xs font-semibold rounded-full mb-4">TECHNOLOGY</span>
        <h2 class="text-3xl md:text-4xl font-bold mb-4 text-gray-900">Advanced Dashboard</h2>
        <p class="text-gray-600 max-w-2xl mx-auto">Intuitive controls and cutting-edge technology at your fingertips.</p>
      </div>
      
      <div class="relative group">
        <img src="/images/city-new-web.png" alt="Honda City Dashboard" class="rounded-xl shadow-xl w-full h-auto transform transition-transform duration-500 group-hover:scale-105" />
        <div class="absolute inset-0 bg-gradient-to-t from-black/50 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 rounded-xl"></div>
      </div>
      
      <div class="grid md:grid-cols-3 gap-8 mt-12">
        <div class="bg-gray-50 p-6 rounded-xl border border-gray-100">
          <div class="w-12 h-12 bg-red-100 rounded-full flex items-center justify-center mb-4">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-red-600" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
            </svg>
          </div>
          <h3 class="text-lg font-bold mb-2">7-inch Touchscreen</h3>
          <p class="text-gray-600">Intuitive interface with Apple CarPlay and Android Auto compatibility.</p>
        </div>
        
        <div class="bg-gray-50 p-6 rounded-xl border border-gray-100">
          <div class="w-12 h-12 bg-red-100 rounded-full flex items-center justify-center mb-4">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-red-600" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2zm10-10V7a4 4 0 00-8 0v4h8z" />
            </svg>
          </div>
          <h3 class="text-lg font-bold mb-2">Remote Engine Start</h3>
          <p class="text-gray-600">Start your car remotely to cool or warm the interior before you enter.</p>
        </div>
        
        <div class="bg-gray-50 p-6 rounded-xl border border-gray-100">
          <div class="w-12 h-12 bg-red-100 rounded-full flex items-center justify-center mb-4">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-red-600" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 15a4 4 0 004 4h9a5 5 0 10-.1-9.999 5.002 5.002 0 10-9.78 2.096A4 4 0 003 15z" />
            </svg>
          </div>
          <h3 class="text-lg font-bold mb-2">Connected Services</h3>
          <p class="text-gray-600">Stay connected with Honda Connect app for vehicle monitoring and control.</p>
        </div>
      </div>
    </section>

    <!-- Exterior -->
    <section class="bg-gradient-to-br from-gray-50 to-gray-100 py-20">
      <div class="max-w-7xl mx-auto px-6">
        <div class="mb-16 text-center">
          <span class="inline-block px-3 py-1 bg-red-100 text-red-800 text-xs font-semibold rounded-full mb-4">EXTERIOR</span>
          <h2 class="text-3xl md:text-4xl font-bold mb-4 text-gray-900">Striking Exterior Features</h2>
          <p class="text-gray-600 max-w-2xl mx-auto">Designed to turn heads with premium finishes and functional details.</p>
        </div>
        
        <div class="grid md:grid-cols-3 gap-8">
          <div class="bg-white rounded-xl overflow-hidden shadow-md border border-gray-100 transform transition-transform duration-300 hover:-translate-y-2">
            <div class="relative group">
              <img src="/images/city-new-web.png" alt="Alloy Wheels" class="w-full h-56 object-cover" />
              <div class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
            </div>
            <div class="p-6">
              <h3 class="text-xl font-bold mb-2">ALLOY WHEELS</h3>
              <p class="text-gray-600">The black and silver 16-inch rims with diamond cut finish enhance the sporty city wheels.</p>
            </div>
          </div>
          
          <div class="bg-white rounded-xl overflow-hidden shadow-md border border-gray-100 transform transition-transform duration-300 hover:-translate-y-2">
            <div class="relative group">
              <img src="/images/city-new-web.png" alt="Retractable Mirrors" class="w-full h-56 object-cover" />
              <div class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
            </div>
            <div class="p-6">
              <h3 class="text-xl font-bold mb-2">RETRACTABLE MIRRORS</h3>
              <p class="text-gray-600">Electric ORVM comes with power fold function for convenience in tight spaces.</p>
            </div>
          </div>
          
          <div class="bg-white rounded-xl overflow-hidden shadow-md border border-gray-100 transform transition-transform duration-300 hover:-translate-y-2">
            <div class="relative group">
              <img src="/images/city-new-web.png" alt="Shark Fin Antenna" class="w-full h-56 object-cover" />
              <div class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
            </div>
            <div class="p-6">
              <h3 class="text-xl font-bold mb-2">SHARK FIN ANTENNA</h3>
              <p class="text-gray-600">Enhances aesthetics while reducing aerodynamic drag for improved efficiency.</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="max-w-7xl mx-auto px-6 py-20">
      <div class="mb-16 text-center">
        <span class="inline-block px-3 py-1 bg-red-100 text-red-800 text-xs font-semibold rounded-full mb-4">INTERIOR</span>
        <h2 class="text-3xl md:text-4xl font-bold mb-4 text-gray-900">Illuminated Instrument Panel</h2>
        <p class="text-gray-600 max-w-2xl mx-auto">Clear, customizable displays for all your driving information.</p>
      </div>
      
      <div class="relative group">
        <img src="/images/city-new-web.png" alt="Honda City Dials" class="rounded-xl shadow-xl w-full h-auto transform transition-transform duration-500 group-hover:scale-105" />
        <div class="absolute inset-0 bg-gradient-to-t from-black/50 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 rounded-xl"></div>
      </div>
      
      <div class="mt-12 bg-gray-50 rounded-xl p-8 max-w-4xl mx-auto">
        <div class="grid md:grid-cols-2 gap-8">
          <div>
            <h3 class="text-xl font-bold mb-4 flex items-center gap-2">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-red-600" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
              </svg>
              Multi-Information Display
            </h3>
            <p class="text-gray-600">Customizable digital display showing fuel economy, trip information, and vehicle alerts.</p>
          </div>
          
          <div>
            <h3 class="text-xl font-bold mb-4 flex items-center gap-2">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-red-600" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
              </svg>
              Steering Wheel Controls
            </h3>
            <p class="text-gray-600">Conveniently mounted controls for audio, phone, and cruise control without taking your hands off the wheel.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Lights -->
    <section class="bg-gradient-to-br from-gray-50 to-gray-100 py-20">
      <div class="max-w-7xl mx-auto px-6">
        <div class="mb-16 text-center">
          <span class="inline-block px-3 py-1 bg-red-100 text-red-800 text-xs font-semibold rounded-full mb-4">SAFETY</span>
          <h2 class="text-3xl md:text-4xl font-bold mb-4 text-gray-900">Advanced Lighting System</h2>
          <p class="text-gray-600 max-w-2xl mx-auto">Enhanced visibility and style with cutting-edge lighting technology.</p>
        </div>
        
        <div class="grid md:grid-cols-2 gap-12 items-center">
          <div class="order-2 md:order-1">
            <div class="space-y-8">
              <div>
                <h3 class="text-2xl font-bold mb-4 text-red-800">FOG LIGHTS</h3>
                <p class="text-gray-600 mb-4">Designed to provide additional light in poor weather conditions, enhancing visibility and safety.</p>
                <ul class="space-y-2 text-gray-600">
                  <li class="flex items-start gap-2">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-red-600 mt-0.5" viewBox="0 0 20 20" fill="currentColor">
                      <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
                    </svg>
                    <span>LED fog lights for brighter, more efficient illumination</span>
                  </li>
                  <li class="flex items-start gap-2">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-red-600 mt-0.5" viewBox="0 0 20 20" fill="currentColor">
                      <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
                    </svg>
                    <span>Integrated design for seamless appearance</span>
                  </li>
                </ul>
              </div>
              
              <div>
                <h3 class="text-2xl font-bold mb-4 text-red-800">TAILLIGHTS</h3>
                <p class="text-gray-600 mb-4">A new bold look that provides added visibility and style with LED light bars.</p>
                <ul class="space-y-2 text-gray-600">
                  <li class="flex items-start gap-2">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-red-600 mt-0.5" viewBox="0 0 20 20" fill="currentColor">
                      <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
                    </svg>
                    <span>Signature LED light bar for distinctive appearance</span>
                  </li>
                  <li class="flex items-start gap-2">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-red-600 mt-0.5" viewBox="0 0 20 20" fill="currentColor">
                      <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
                    </svg>
                    <span>Enhanced visibility for safer driving in all conditions</span>
                  </li>
                </ul>
              </div>
            </div>
          </div>
          
          <div class="order-1 md:order-2 relative group">
            <img src="/images/city-new-web.png" alt="Honda City Taillight" class="rounded-xl shadow-xl w-full h-auto transform transition-transform duration-500 group-hover:scale-105" />
            <div class="absolute inset-0 bg-gradient-to-t from-black/50 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 rounded-xl"></div>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="bg-gradient-to-r from-red-700 to-red-800 py-20">
      <div class="max-w-4xl mx-auto px-6 text-center text-white">
        <h2 class="text-3xl md:text-4xl font-bold mb-6">Experience the Honda City Today</h2>
        <p class="text-xl mb-10 max-w-2xl mx-auto">Visit your nearest Honda dealership or book a test drive to feel the difference.</p>
        <div class="flex flex-wrap justify-center gap-4">
          <button class="px-8 py-4 bg-white text-red-700 hover:bg-gray-100 font-bold rounded-lg transition-all duration-300 transform hover:scale-105">
            Book a Test Drive
          </button>
        </div>
      </div>
    </section>
  </section>
</template>

<script setup>
// Component logic can be added here if needed
</script>

<style scoped>
@keyframes fade-in {
  from { opacity: 0; }
  to { opacity: 1; }
}

.animate-fade-in {
  animation: fade-in 0.8s ease-out forwards;
}

.delay-150 {
  animation-delay: 0.15s;
  opacity: 0;
}

.delay-300 {
  animation-delay: 0.3s;
  opacity: 0;
}

.delay-500 {
  animation-delay: 0.5s;
  opacity: 0;
}

/* Custom animation for pulse-slow */
@keyframes pulse-slow {
  0%, 100% { opacity: 0.1; }
  50% { opacity: 0.2; }
}

.animate-pulse-slow {
  animation: pulse-slow 8s cubic-bezier(0.4, 0, 0.6, 1) infinite;
}

.delay-1000 {
  animation-delay: 1s;
}
</style>