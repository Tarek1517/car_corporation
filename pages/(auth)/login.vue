<script setup>
import { ref } from 'vue';
import { Icon } from '@iconify/vue';
import { toast } from 'vue3-toastify';
definePageMeta({
  layout:'guest'
})
const passwordVisible = ref(false);
const isLoading = ref(false);
const email = ref('');
const password = ref('');

const togglePasswordVisibility = () => {
  passwordVisible.value = !passwordVisible.value;
};

const handleLogin = async () => {
  if (!email.value || !password.value) {
    toast('Please fill in all fields');
    return;
  }
  
  isLoading.value = true;
  setTimeout(() => {
    isLoading.value = false;
    alert('Login successful!');
  }, 1500);
};
</script>

<template>
  <section class="relative w-full min-h-screen overflow-hidden bg-gradient-to-br from-gray-50 via-white to-gray-100">    
    <div class="relative z-10">
      <div class="flex flex-col md:flex-row min-h-screen">
        <div class="hidden lg:block lg:w-1/2 xl:w-2/3 relative">
          <div class="absolute inset-0 bg-gradient-to-r from-primary-500/20 to-secondary-500/20 z-10"></div>
          <img src="/images/login.jpg" 
               alt="Login background" 
               class="w-full h-full object-cover">
          <div class="absolute inset-0 flex items-center justify-center z-20">
            <div class="text-center p-8 bg-white/20 backdrop-blur-sm rounded-2xl border border-white/30 max-w-5xl">
              <h1 class="text-4xl font-bold text-white mb-4">Welcome Back To Car Corporation</h1>
              <p class="text-white/90 text-lg">Sign in to access your personalized dashboard and continue your journey with us.</p>
            </div>
          </div>
        </div>

        <div class="w-full lg:w-1/3 xl:w-1/2 flex items-center justify-center p-6 lg:p-12">
          <div class="w-full max-w-3xl bg-white rounded-2xl shadow-xl p-8 lg:p-10 transition-all duration-300 hover:shadow-2xl">
            <div class="text-center mb-10">
              <h1 class="text-3xl font-bold text-gray-800">Log in to your account</h1>
              <p class="text-gray-600 mt-2">Please enter your details</p>
            </div>
            
            <form @submit.prevent="handleLogin" class="space-y-6">
              <div>
                <label class="block text-gray-700 font-medium mb-2" for="email">Email Address</label>
                <div class="relative">
                  <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
                    <Icon icon="mdi:email" class="h-5 w-5 text-gray-400" />
                  </div>
                  <input 
                    type="email" 
                    id="email"
                    v-model="email"
                    placeholder="Enter Email Address" 
                    class="w-full pl-10 pr-4 py-3 rounded-lg border text-gray-700 placeholder-text-gray-500 border-gray-300 bg-gray-50 focus:bg-white focus:outline-none focus:ring-2 focus:ring-primary transition"
                    required 
                  />
                </div>
              </div>
              
              <div>
                <label class="block text-gray-700 font-medium mb-2" for="password">Password</label>
                <div class="relative">
                  <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
                    <Icon icon="mdi:lock" class="h-5 w-5 text-gray-400" />
                  </div>
                  <input 
                    :type="passwordVisible ? 'text' : 'password'"
                    id="password"
                    v-model="password"
                    placeholder="Enter Password" 
                    minlength="6"
                    class="w-full pl-10 pr-12 py-3 rounded-lg border border-gray-300 text-gray-700 placeholder-text-gray-500 bg-gray-50 focus:bg-white focus:outline-none focus:ring-2 focus:ring-primary transition"
                    required 
                  />
                  <button 
                    type="button"
                    @click="togglePasswordVisibility"
                    class="absolute inset-y-0 right-0 pr-3 flex items-center"
                  >
                    <Icon v-if="!passwordVisible" icon="mdi:eye" class="h-5 w-5 text-gray-500 hover:text-primary" />
                    <Icon v-else icon="mdi:eye-off" class="h-5 w-5 text-gray-500 hover:text-primary" />
                  </button>
                </div>
              </div>
              
              <div class="flex items-center justify-between">
                <div class="flex items-center">
                  <input id="remember-me" name="remember-me" type="checkbox" class="h-4 w-4 text-primary focus:ring-primary border-gray-300 rounded">
                  <label for="remember-me" class="ml-2 block text-sm text-gray-700">Remember me</label>
                </div>
                <div class="text-sm">
                  <a href="#" class="font-medium text-primary hover:text-primary-dark transition">Forgot password?</a>
                </div>
              </div>
              
              <button 
                type="submit" 
                :disabled="isLoading"
                class="w-full flex justify-center py-3 px-4 border border-transparent rounded-lg shadow-sm text-sm font-medium text-white bg-gradient-to-r from-primary to-secondary hover:from-primary-dark hover:to-secondary-dark focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-primary transition-all duration-300 transform hover:-translate-y-0.5 disabled:opacity-75 disabled:cursor-not-allowed"
              >
                <Icon v-if="isLoading" icon="mdi:loading" class="animate-spin -ml-1 mr-3 h-5 w-5 text-white" />
                {{ isLoading ? 'Logging in...' : 'Log in' }}
              </button>
            </form>
<!--             
            <div class="mt-6">
              <div class="relative">
                <div class="absolute inset-0 flex items-center">
                  <div class="w-full border-t border-gray-300"></div>
                </div>
                <div class="relative flex justify-center text-sm">
                  <span class="px-2 bg-white text-gray-500">Or continue with</span>
                </div>
              </div>
              
              <div class="mt-6">
                <button class="w-full flex items-center justify-center px-4 py-3 border border-gray-300 rounded-lg shadow-sm bg-white text-sm font-medium text-gray-700 hover:bg-gray-50 transition">
                  <Icon icon="logos:google-icon" class="w-5 h-5 mr-3" />
                  Sign in with Google
                </button>
              </div>
            </div>
            <div class="mt-6">
              <div class="">
                <button class="w-full flex items-center justify-center px-4 py-3 border border-gray-300 rounded-lg shadow-sm bg-white text-sm font-medium text-gray-700 hover:bg-gray-50 transition">
                  <Icon icon="logos:facebook" class="w-5 h-5 mr-3" />
                  Sign in with Facebook
                </button>
              </div>
            </div> -->
            <div class="mt-8 text-center">
              <p class="text-gray-600">
                Don't have an account? 
                <NuxtLink href="/register" class="font-medium text-primary hover:text-primary-dark transition">Register</NuxtLink>
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
@keyframes blob {
  0% {
    transform: translate(0px, 0px) scale(1);
  }
  33% {
    transform: translate(30px, -50px) scale(1.1);
  }
  66% {
    transform: translate(-20px, 20px) scale(0.9);
  }
  100% {
    transform: translate(0px, 0px) scale(1);
  }
}
.animate-blob {
  animation: blob 7s infinite;
}
.animation-delay-2000 {
  animation-delay: 2s;
}
.animation-delay-4000 {
  animation-delay: 4s;
}
</style>
