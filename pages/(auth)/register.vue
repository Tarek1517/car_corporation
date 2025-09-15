<script setup>
import { ref } from 'vue';
import { Icon } from '@iconify/vue';
import { toast } from 'vue3-toastify';
definePageMeta({
  layout:'guest'
})
const passwordVisible = ref(false);
const confirmPasswordVisible = ref(false);
const isLoading = ref(false);
const fullName = ref('');
const email = ref('');
const password = ref('');
const confirmPassword = ref('');
const selectedImage = ref(null);
const imagePreview = ref(null);

const togglePasswordVisibility = () => {
  passwordVisible.value = !passwordVisible.value;
};

const toggleConfirmPasswordVisibility = () => {
  confirmPasswordVisible.value = !confirmPasswordVisible.value;
};

const handleImageUpload = (event) => {
  const file = event.target.files[0];
  if (file) {
    // Check if file is an image
    if (!file.type.match('image.*')) {
      toast('Please select an image file');
      return;
    }
    
    // Check file size (limit to 5MB)
    if (file.size > 5 * 1024 * 1024) {
      toast('Image size should be less than 5MB');
      return;
    }
    
    selectedImage.value = file;
    
    // Create preview
    const reader = new FileReader();
    reader.onload = (e) => {
      imagePreview.value = e.target.result;
    };
    reader.readAsDataURL(file);
  }
};

const removeImage = () => {
  selectedImage.value = null;
  imagePreview.value = null;
  // Reset file input
  if (document.getElementById('image-upload')) {
    document.getElementById('image-upload').value = '';
  }
};

const triggerFileInput = () => {
  document.getElementById('image-upload').click();
};

const handleRegister = async () => {
  if (!fullName.value || !email.value || !password.value || !confirmPassword.value) {
    toast('Please fill in all fields');
    return;
  }
  
  if (password.value !== confirmPassword.value) {
    toast('Passwords do not match');
    return;
  }
  
  if (password.value.length < 8) {
    toast('Password must be at least 8 characters long');
    return;
  }
  
  isLoading.value = true;
  setTimeout(() => {
    isLoading.value = false;
    alert('Registration successful!');
  }, 1500);
};
</script>

<template>
  <section class="relative w-full min-h-screen overflow-hidden bg-gradient-to-br from-gray-50 via-white to-gray-100">    
    <div class="relative z-10">
      <div class="flex flex-col md:flex-row min-h-screen">
        <div class="w-full lg:w-1/3 xl:w-1/2 flex items-center justify-center p-6 lg:p-12">
          <div class="w-full max-w-3xl bg-white rounded-2xl shadow-xl p-8 lg:p-10 transition-all duration-300 hover:shadow-2xl">
            <div class="text-center mb-10">
              <div class="relative mx-auto w-20 h-20 mb-4">
                <div 
                  class="w-full h-full bg-gradient-to-r from-primary to-secondary rounded-full flex items-center justify-center cursor-pointer overflow-hidden"
                  @click="triggerFileInput"
                >
                  <div v-if="!imagePreview" class="flex flex-col items-center">
                    <Icon icon="material-symbols:account-circle" class="h-10 w-10 text-white" />
                    <span class="text-xs text-white mt-1">Upload</span>
                  </div>
                  <img 
                    v-else 
                    :src="imagePreview" 
                    alt="Profile preview" 
                    class="w-full h-full object-cover"
                  >
                </div>
                
                <button 
                  v-if="imagePreview"
                  @click.stop="removeImage"
                  class="absolute -top-1 -right-1 bg-red-500 text-white rounded-full p-1 hover:bg-red-600 transition"
                >
                  <Icon icon="mdi:close" class="h-4 w-4" />
                </button>
                
                <input 
                  id="image-upload"
                  type="file" 
                  accept="image/*" 
                  class="hidden" 
                  @change="handleImageUpload"
                >
              </div>
              
              <h1 class="text-3xl font-bold text-gray-800">Create an account</h1>
              <p class="text-gray-600 mt-2">Please enter your details to register</p>
            </div>
            
            <form @submit.prevent="handleRegister" class="space-y-6">
              <div>
                <label class="block text-gray-700 font-medium mb-2" for="fullName">Full Name</label>
                <div class="relative">
                  <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
                    <Icon icon="mdi:account" class="h-5 w-5 text-gray-400" />
                  </div>
                  <input 
                    type="text" 
                    id="fullName"
                    v-model="fullName"
                    placeholder="Enter your full name" 
                    class="w-full pl-10 pr-4 py-3 rounded-lg border text-gray-700 placeholder-text-gray-500 border-gray-300 bg-gray-50 focus:bg-white focus:outline-none focus:ring-2 focus:ring-primary transition"
                    required 
                  />
                </div>
              </div>
              
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
                    minlength="8"
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
              
              <div>
                <label class="block text-gray-700 font-medium mb-2" for="confirmPassword">Confirm Password</label>
                <div class="relative">
                  <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
                    <Icon icon="mdi:lock-check" class="h-5 w-5 text-gray-400" />
                  </div>
                  <input 
                    :type="confirmPasswordVisible ? 'text' : 'password'"
                    id="confirmPassword"
                    v-model="confirmPassword"
                    placeholder="Confirm Password" 
                    minlength="8"
                    class="w-full pl-10 pr-12 py-3 rounded-lg border border-gray-300 text-gray-700 placeholder-text-gray-500 bg-gray-50 focus:bg-white focus:outline-none focus:ring-2 focus:ring-primary transition"
                    required 
                  />
                  <button 
                    type="button"
                    @click="toggleConfirmPasswordVisibility"
                    class="absolute inset-y-0 right-0 pr-3 flex items-center"
                  >
                    <Icon v-if="!confirmPasswordVisible" icon="mdi:eye" class="h-5 w-5 text-gray-500 hover:text-primary" />
                    <Icon v-else icon="mdi:eye-off" class="h-5 w-5 text-gray-500 hover:text-primary" />
                  </button>
                </div>
              </div>
              
              <div class="flex items-center">
                <input id="agree-terms" name="agree-terms" type="checkbox" class="h-4 w-4 text-primary focus:ring-primary border-gray-300 rounded">
                <label for="agree-terms" class="ml-2 block text-sm text-gray-700">
                  I agree to the <a href="#" class="text-primary hover:text-primary-dark transition">Terms and Conditions</a> and <a href="#" class="text-primary hover:text-primary-dark transition">Privacy Policy</a>
                </label>
              </div>
              
              <button 
                type="submit" 
                :disabled="isLoading"
                class="w-full flex justify-center py-3 px-4 border border-transparent rounded-lg shadow-sm text-sm font-medium text-white bg-gradient-to-r from-primary to-secondary hover:from-primary-dark hover:to-secondary-dark focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-primary transition-all duration-300 transform hover:-translate-y-0.5 disabled:opacity-75 disabled:cursor-not-allowed"
              >
                <Icon v-if="isLoading" icon="mdi:loading" class="animate-spin -ml-1 mr-3 h-5 w-5 text-white" />
                {{ isLoading ? 'Creating account...' : 'Create account' }}
              </button>
            </form>
            
            <div class="mt-8 text-center">
              <p class="text-gray-600">
                Already have an account? 
                <NuxtLink to="/login" class="font-medium text-primary hover:text-primary-dark transition">Log in</NuxtLink>
              </p>
            </div>
          </div>
        </div>
        <div class="hidden lg:block lg:w-1/2 xl:w-2/3 relative">
          <div class="absolute inset-0 bg-gradient-to-r from-primary-500/20 to-secondary-500/20 z-10"></div>
          <img src="/images/register.jpg" 
               alt="Registration background" 
               class="w-full h-full object-cover">
          <div class="absolute inset-0 flex items-center justify-center z-20">
            <div class="text-center p-8 bg-white/20 backdrop-blur-sm rounded-2xl border border-white/30 max-w-5xl">
              <h1 class="text-4xl font-bold text-white mb-4">Join Car Corporation Today</h1>
              <p class="text-white/90 text-lg">Create an account to access exclusive features and start your journey with us.</p>
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