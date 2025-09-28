<script setup>
import { ref } from 'vue';
import { Icon } from "@iconify/vue"; 

// Form data refs
const manufacturer = ref('');
const model = ref('');
const year = ref('');
const preferredGrade = ref('');
const preferredColor = ref('');
const preferredMileage = ref('');
const deliveryDate = ref('');
const description = ref('');

const name = ref('');
const contactNo = ref('');
const email = ref('');
const address = ref('');

// Form validation
const formSubmitted = ref(false);
const errors = ref({});

const validateForm = () => {
  errors.value = {};
  
  if (!manufacturer.value) errors.value.manufacturer = "Manufacturer is required";
  if (!model.value) errors.value.model = "Model is required";
  if (!name.value) errors.value.name = "Name is required";
  if (!contactNo.value) errors.value.contactNo = "Contact number is required";
  if (!email.value) {
    errors.value.email = "Email is required";
  } else if (!/^\S+@\S+\.\S+$/.test(email.value)) {
    errors.value.email = "Please enter a valid email";
  }
  
  return Object.keys(errors.value).length === 0;
};

const submitForm = () => {
  formSubmitted.value = true;
  
  if (!validateForm()) {
    // Scroll to first error
    const firstError = Object.keys(errors.value)[0];
    const element = document.querySelector(`[data-field="${firstError}"]`);
    if (element) {
      element.scrollIntoView({ behavior: 'smooth', block: 'center' });
    }
    return;
  }

  const formData = {
    manufacturer: manufacturer.value,
    model: model.value,
    year: year.value,
    preferredGrade: preferredGrade.value,
    preferredColor: preferredColor.value,
    preferredMileage: preferredMileage.value,
    deliveryDate: deliveryDate.value,
    description: description.value,
    name: name.value,
    contactNo: contactNo.value,
    email: email.value,
    address: address.value,
  };

  console.log('Form data:', formData);
  alert('Form submitted successfully! We will contact you shortly.');
  
  // Reset form after submission
  resetForm();
};

const resetForm = () => {
  manufacturer.value = '';
  model.value = '';
  year.value = '';
  preferredGrade.value = '';
  preferredColor.value = '';
  preferredMileage.value = '';
  deliveryDate.value = '';
  description.value = '';
  name.value = '';
  contactNo.value = '';
  email.value = '';
  address.value = '';
  formSubmitted.value = false;
  errors.value = {};
};
</script>

<template>
  <section class="w-full relative overflow-hidden">

    <section class="relative">
      <div class="relative h-[500px] md:h-[600px] w-full overflow-hidden">
        <img src="../../public/images/pre-order-2.jpg" alt="Pre Order Car"
             class="w-full h-full object-cover brightness-75" />
        <div class="absolute inset-0 bg-gradient-to-r from-black/70 to-black/40"></div>
        
        <div class="absolute inset-0 flex flex-col items-start justify-center px-10 md:px-20 text-left z-10 max-w-7xl">
          <h2 class="text-5xl md:text-7xl font-bold text-white mb-4 drop-shadow-lg">
            Pre
            <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">
              Order
            </span>
          </h2>
          <p class="text-xl md:text-2xl text-white max-w-2xl drop-shadow-md mb-8">
            Secure your dream car directly from Auctions with ease.  
            Reserve today and let us handle everything—from bidding to delivery at your doorstep.
          </p>
        </div>
      </div>
    </section>
    
    <section class="relative overflow-hidden py-6 md:py-10 bg-gradient-to-br from-slate-50 via-white to-slate-100">
      <div class="container mx-auto px-4 md:px-6">
        <div class="text-center mb-10">
          <h3 class="text-3xl font-bold text-gray-800 mb-3">Vehicle Specifications</h3>
          <p class="text-gray-600 max-w-2xl mx-auto">Tell us about your dream car. The more details you provide, the better we can match your preferences.</p>
        </div>
        
        <div class="bg-white rounded-xl shadow-lg overflow-hidden max-w-6xl mx-auto">
          <div class="grid grid-cols-1 md:grid-cols-3 gap-0">
            <div class="md:col-span-2 p-6 md:p-8">
              <div class="grid grid-cols-1 md:grid-cols-2 gap-5 mb-6">
                <div data-field="manufacturer">
                  <label class="block text-gray-700 font-semibold mb-2 flex items-center">
                    Manufacturer
                    <span class="text-red-500 ml-1">*</span>
                  </label>
                  <select
                    v-model="manufacturer"
                    :class="{'border-red-500': formSubmitted && errors.manufacturer}"
                    class="w-full p-3 border border-gray-300 placeholder-gray-400 text-gray-600 rounded-lg shadow-sm focus:outline-none focus:ring-2 focus:ring-primary focus:border-transparent transition-all"
                  >
                    <option value="" disabled selected>Select Manufacturer</option>
                    <option value="toyota">Toyota</option>
                    <option value="honda">Honda</option>
                    <option value="nissan">Nissan</option>
                    <option value="mazda">Mazda</option>
                    <option value="subaru">Subaru</option>
                    <option value="mitsubishi">Mitsubishi</option>
                  </select>
                  <p v-if="formSubmitted && errors.manufacturer" class="text-red-500 text-sm mt-1 flex items-center">
                    <Icon icon="mdi:alert-circle" class="mr-1" /> {{ errors.manufacturer }}
                  </p>
                </div>

                <div data-field="model">
                  <label class="block text-gray-700 font-semibold mb-2 flex items-center">
                    Model
                    <span class="text-red-500 ml-1">*</span>
                  </label>
                  <select
                    v-model="model"
                    :class="{'border-red-500': formSubmitted && errors.model}"
                    class="w-full p-3 border border-gray-300 placeholder-gray-400 text-gray-600 rounded-lg shadow-sm focus:outline-none focus:ring-2 focus:ring-primary focus:border-transparent transition-all"
                  >
                    <option value="" disabled selected>Select Model</option>
                    <option v-if="manufacturer === 'toyota'" value="aqua">Aqua</option>
                    <option v-if="manufacturer === 'toyota'" value="prius">Prius</option>
                    <option v-if="manufacturer === 'toyota'" value="corolla">Corolla</option>
                    <option v-if="manufacturer === 'honda'" value="fit">Fit</option>
                    <option v-if="manufacturer === 'honda'" value="civic">Civic</option>
                    <option v-if="manufacturer === 'nissan'" value="note">Note</option>
                    <option v-if="manufacturer === 'nissan'" value="march">March</option>
                  </select>
                  <p v-if="formSubmitted && errors.model" class="text-red-500 text-sm mt-1 flex items-center">
                    <Icon icon="mdi:alert-circle" class="mr-1" /> {{ errors.model }}
                  </p>
                </div>

                <div>
                  <label class="block text-gray-700 font-semibold mb-2">Year</label>
                  <select
                    v-model="year"
                    class="w-full p-3 border border-gray-300 rounded-lg placeholder-gray-400 text-gray-600 shadow-sm focus:outline-none focus:ring-2 focus:ring-primary focus:border-transparent transition-all"
                  >
                    <option value="" disabled selected>Select Year</option>
                    <option v-for="y in 10" :value="2024 - y + 1">{{ 2024 - y + 1 }}</option>
                  </select>
                </div>

                <div>
                  <label class="block text-gray-700 font-semibold mb-2">Preferred Grade</label>
                  <select
                    v-model="preferredGrade"
                    class="w-full p-3 border border-gray-300 rounded-lg placeholder-gray-400 text-gray-600 shadow-sm focus:outline-none focus:ring-2 focus:ring-primary focus:border-transparent transition-all"
                  >
                    <option value="" disabled selected>Select Grade</option>
                    <option value="g">G Grade</option>
                    <option value="s">S Grade</option>
                    <option value="x">X Grade</option>
                    <option value="r">R Grade</option>
                  </select>
                </div>


                <div>
                  <label class="block text-gray-700 font-semibold mb-2">Preferred Mileage (km)</label>
                  <div class="relative">
                    <input
                      v-model="preferredMileage"
                      type="number"
                      placeholder="Enter Mileage"
                      min="0"
                      class="w-full p-3 border placeholder-gray-400 text-gray-600 border-gray-300 rounded-lg shadow-sm focus:outline-none focus:ring-2 focus:ring-primary focus:border-transparent transition-all"
                    />
                    <div class="absolute inset-y-0 right-0 flex items-center pr-3 pointer-events-none">
                      <span class="text-gray-500">km</span>
                    </div>
                  </div>
                </div>
                
              <div>
                <label class="block text-gray-700 font-semibold mb-2">Preferred Delivery Date</label>
                <div class="relative">
                  <input
                    v-model="deliveryDate"
                    type="date"
                    :min="new Date().toISOString().split('T')[0]"
                    class="w-full p-3 border border-gray-300 placeholder-gray-400 text-gray-600 rounded-lg shadow-sm focus:outline-none focus:ring-2 focus:ring-primary focus:border-transparent transition-all"
                  />
                  <div class="absolute inset-y-0 right-0 flex items-center pr-3 pointer-events-none">
                    <Icon icon="mdi:calendar" class="h-5 w-5 text-primary" />
                  </div>
                </div>
              </div>
              </div>

              <div>
                <label class="block text-gray-700 font-semibold mb-2">Additional Requirements</label>
                <textarea
                  v-model="description"
                  rows="4"
                  placeholder="Any specific features or requirements you're looking for..."
                  class="w-full p-3 border border-gray-300 rounded-lg placeholder-gray-400 text-gray-600 shadow-sm focus:outline-none focus:ring-2 focus:ring-primary focus:border-transparent transition-all"
                ></textarea>
              </div>
            </div>

            <div class="bg-gradient-to-br from-primary to-secondary p-6 md:p-8 text-white flex flex-col">
              <div>
                <h3 class="text-xl font-bold mb-6 pb-2 border-b border-white/20">Your Contact Information</h3>
                
                <div class="mb-5" data-field="name">
                  <label class="block text-sm font-semibold mb-2 flex items-center">
                    Full Name
                    <span class="text-red-300 ml-1">*</span>
                  </label>
                  <div class="relative">
                    <input
                      v-model="name"
                      :class="{'border-red-300': formSubmitted && errors.name}"
                      type="text"
                      placeholder="Your full name"
                      class="w-full p-3 rounded-lg bg-white/90 text-gray-900 placeholder-gray-500 border-none focus:outline-none focus:ring-2 focus:ring-white/70 transition-all"
                    />
                    <div class="absolute inset-y-0 right-0 flex items-center pr-3">
                      <Icon icon="mdi:account" class="h-5 w-5 text-primary" />
                    </div>
                  </div>
                  <p v-if="formSubmitted && errors.name" class="text-red-200 text-sm mt-1 flex items-center">
                    <Icon icon="mdi:alert-circle" class="mr-1" /> {{ errors.name }}
                  </p>
                </div>

                <div class="mb-5" data-field="contactNo">
                  <label class="block text-sm font-semibold mb-2 flex items-center">
                    Contact Number
                    <span class="text-red-300 ml-1">*</span>
                  </label>
                  <div class="flex items-center">
                    <span class="p-3 border border-white/30 bg-white/10 rounded-l-lg font-bold">+88</span>
                    <input
                      v-model="contactNo"
                      :class="{'border-red-300': formSubmitted && errors.contactNo}"
                      type="tel"
                      placeholder="Your phone number"
                      class="w-full p-3 rounded-r-lg bg-white/90 text-gray-900 border-none placeholder-gray-500 focus:outline-none focus:ring-2 focus:ring-white/70 transition-all"
                    />
                  </div>
                  <p v-if="formSubmitted && errors.contactNo" class="text-red-200 text-sm mt-1 flex items-center">
                    <Icon icon="mdi:alert-circle" class="mr-1" /> {{ errors.contactNo }}
                  </p>
                </div>

                <div class="mb-5" data-field="email">
                  <label class="block text-sm font-semibold mb-2 flex items-center">
                    Email Address
                    <span class="text-red-300 ml-1">*</span>
                  </label>
                  <div class="relative">
                    <input
                      v-model="email"
                      :class="{'border-red-300': formSubmitted && errors.email}"
                      type="email"
                      placeholder="Enter your Email"
                      class="w-full p-3 rounded-lg bg-white/90 text-gray-900 placeholder-gray-500 border-none focus:outline-none focus:ring-2 focus:ring-white/70 transition-all"
                    />
                    <div class="absolute inset-y-0 right-0 flex items-center pr-3">
                      <Icon icon="mdi:email" class="h-5 w-5 text-primary" />
                    </div>
                  </div>
                  <p v-if="formSubmitted && errors.email" class="text-red-200 text-sm mt-1 flex items-center">
                    <Icon icon="mdi:alert-circle" class="mr-1" /> {{ errors.email }}
                  </p>
                </div>

                <div class="mb-5">
                  <label class="block text-sm font-semibold mb-2">Delivery Address</label>
                  <textarea
                    v-model="address"
                    rows="3"
                    placeholder="Your complete address for delivery"
                    class="w-full p-3 rounded-lg bg-white/90 text-gray-900 placeholder-gray-500 border-none focus:outline-none focus:ring-2 focus:ring-white/70 transition-all"
                  ></textarea>
                </div>
              </div>

              <div class="mt-6 pt-4 border-t border-white/20">
                <button 
                  @click="submitForm" 
                  class="w-full py-3 px-6 bg-white text-primary rounded-lg font-semibold flex items-center justify-center hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-white/50 transition-all shadow-md hover:shadow-lg hover:bg-primary hover:text-white"
                >
                  <span>Submit Pre-Order</span>
                  <Icon icon="material-symbols:send-rounded" class="h-5 w-5 ml-2 transform -rotate-45" />
                </button>
                
                <p class="text-white/80 text-xs mt-4 text-center">
                  By submitting this form, you agree to our 
                  <a href="#" class="underline hover:text-white">Terms of Service</a> and 
                  <a href="#" class="underline hover:text-white">Privacy Policy</a>
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </section>
</template>

<style scoped>
input:focus, select:focus, textarea:focus {
  box-shadow: 0 0 0 3px rgba(66, 153, 225, 0.2);
}

input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

input[type=number] {
  -moz-appearance: textfield;
}
</style>