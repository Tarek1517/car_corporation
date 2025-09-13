<script setup>
import { Icon } from '@iconify/vue';
import { ref, computed } from 'vue';
import CarOverview from './carOverview.vue';

// Inputs
const fob = ref(0);
const freight = ref(0);
const insurance = ref(0);
const otherFees = ref(0);
const exchangeRate = ref(110); // default; change as needed
const currency = ref('USD'); // USD or BDT

// Editable rates (set defaults; user can change)
const rates = ref({
  customs: 25.0, // default percentage — change to match local rules
  vat: 15.0,
  ait: 4.0
});

const calculated = ref(false);
const timestamp = ref('');

// Helper: convert (if currency is USD and user wants BDT, we render in BDT)
const displayCurrency = computed(() => currency.value === 'USD' ? 'USD' : 'BDT');

// Displayed amount helper: if user selected BDT and input was USD, we convert.
// For simplicity: we assume user inputs values in the selected currency.
// Use exchangeRate only when converting is needed (this component treats
// numbers as entered in the chosen currency).
const displayed = (amount) => amount; // amount already in display currency

// Calculations (recomputed when calculate is called)
const cif = ref(0);
const customsDuty = ref(0);
const vatBase = ref(0);
const vat = ref(0);
const ait = ref(0);
const total = ref(0);

function calculate() {
  // normalize NaN
  const _fob = Number(fob.value) || 0;
  const _freight = Number(freight.value) || 0;
  const _insurance = Number(insurance.value) || 0;
  const _other = Number(otherFees.value) || 0;

  // CIF
  cif.value = round2(_fob + _freight + _insurance);

  // Customs
  customsDuty.value = round2(cif.value * (Number(rates.value.customs) / 100));

  // VAT base = CIF + customs
  vatBase.value = round2(cif.value + customsDuty.value);

  // VAT and AIT
  vat.value = round2(vatBase.value * (Number(rates.value.vat) / 100));
  ait.value = round2(vatBase.value * (Number(rates.value.ait) / 100));

  // Total
  total.value = round2(cif.value + customsDuty.value + vat.value + ait.value + _other);

  calculated.value = true;
  timestamp.value = new Date().toLocaleString();
}

function reset() {
  fob.value = 0;
  freight.value = 0;
  insurance.value = 0;
  otherFees.value = 0;
  rates.value = { customs: 25.0, vat: 15.0, ait: 4.0 };
  exchangeRate.value = 110;
  currency.value = 'USD';
  calculated.value = false;
  timestamp.value = '';
  cif.value = customsDuty.value = vatBase.value = vat.value = ait.value = total.value = 0;
}

function round2(n) {
  return Math.round((n + Number.EPSILON) * 100) / 100;
}

// Number formatter
const fmt = (val) => {
  if (val === null || val === undefined) return '-';
  return new Intl.NumberFormat('en-US', { minimumFractionDigits: 2, maximumFractionDigits: 2 }).format(val);
}

// Copy summary to clipboard
async function copySummary() {
  if (!calculated.value) return;
  const text = [
    `Duty calculation (${timestamp.value})`,
    `FOB: ${fmt(displayed(fob.value))} ${displayCurrency.value}`,
    `Freight: ${fmt(displayed(freight.value))} ${displayCurrency.value}`,
    `Insurance: ${fmt(displayed(insurance.value))} ${displayCurrency.value}`,
    `CIF: ${fmt(displayed(cif.value))} ${displayCurrency.value}`,
    `Customs (${rates.value.customs}%): ${fmt(displayed(customsDuty.value))} ${displayCurrency.value}`,
    `VAT (${rates.value.vat}%): ${fmt(displayed(vat.value))} ${displayCurrency.value}`,
    `AIT (${rates.value.ait}%): ${fmt(displayed(ait.value))} ${displayCurrency.value}`,
    `Other fees: ${fmt(displayed(otherFees.value))} ${displayCurrency.value}`,
    `Total payable: ${fmt(displayed(total.value))} ${displayCurrency.value}`
  ].join('\n');

  try {
    await navigator.clipboard.writeText(text);
    alert('Summary copied to clipboard');
  } catch (e) {
    alert('Unable to copy. Here is the summary:\n\n' + text);
  }
}
const cars = ref([
  { src: "/images/crossred.jpeg", label: "Low Mileage" },
  { src: "/images/Rav4.jpeg" },
  { src: "/images/rav4-1.jpg" },
  { src: "/images/rav4-2.png" },
  { src: "/images/rav4-3.jpg" },
]);

const showModal = ref(false);
const activeImage = ref(null);

const openModal = (src) => {
  activeImage.value = src;
  showModal.value = true;
};

const closeModal = () => {
  showModal.value = false;
  activeImage.value = null;
};
</script>

<template>
  <section class="w-full relative overflow-hidden bg-gradient-to-br from-slate-50 via-white to-slate-100">
    <div
      class="absolute top-0 right-0 w-96 h-96 bg-primary/10 rounded-full -translate-y-1/3 translate-x-1/3 blur-3xl animate-pulse-slow">
    </div>
    <div
      class="absolute bottom-0 left-0 w-[32rem] h-[32rem] bg-secondary/10 rounded-full translate-y-1/3 -translate-x-1/3 blur-3xl animate-pulse-slow delay-1000">
    </div>
    <div class="absolute top-1/2 left-1/4 w-64 h-64 bg-primary/5 rounded-full blur-3xl animate-pulse-slow delay-500">
    </div>
    <div class="absolute inset-0 opacity-[0.03] bg-grid-pattern"></div>

    <section class="relative z-10 py-2">
      <div class="min-h-screen bg-gray-50">
        <div class="container mx-auto px-4 py-2">
          <div class="mb-8">
            <h1 class="text-3xl font-bold text-gray-900">Toyota RAV4</h1>
            <div class="flex items-center mt-2">
              <span class="text-3xl font-bold text-primary">$32,450</span>
              <span class="ml-4 bg-red-100 text-primary px-3 py-1 rounded-full text-sm">Used</span>
            </div>
          </div>

          <div class="text-start mx-auto font-normal text-gray-700">
            4.0 D5 PowerPulse Momentum 5dr AWD Geartronic Estate
          </div>
          <div class="flex items-center mx-auto font-normal py-2 gap-4">
            <span class="bg-red-100 text-primary px-3 py-1 rounded-full text-sm flex font-semibold">
              <Icon icon="line-md:calendar" class="w-5 h-5 text-red-600 mr-2" /> 2022
            </span>
            <span class="bg-red-100 text-primary px-3 py-1 rounded-full text-sm flex font-semibold">
              <Icon icon="line-md:home" class="w-5 h-5 text-red-600 mr-2" /> Tokyo
            </span>
            <span class="bg-red-100 text-primary px-3 py-1 rounded-full text-sm flex font-semibold">
              <Icon icon="line-md:speedometer-loop" class="w-5 h-5 text-red-600 mr-2" /> 18,240 mi
            </span>
            <span class="bg-red-100 text-primary px-3 py-1 rounded-full text-sm flex font-semibold">
              <Icon icon="mdi:gas-station" class="w-5 h-5 text-red-600 mr-2" /> Petrol
            </span>
          </div>
          <section class="max-w-7xl mx-auto p-4">
            <div class="grid grid-cols-1 md:grid-cols-3 gap-3">
              <div class="relative md:col-span-2">
                <img :src="cars[0].src" class="w-full h-[420px] object-cover rounded-lg cursor-pointer" alt="Main Car"
                  @click="openModal(cars[0].src)" />
              </div>
              <div class="grid grid-cols-2 gap-3">
                <div v-for="(car, index) in cars.slice(1)" :key="index" class="relative">
                  <img :src="car.src" class="w-full h-[200px] object-cover rounded-lg cursor-pointer" alt="Car image"
                    @click="openModal(car.src)" />
                </div>
              </div>
            </div>
          </section>
        </div>
      </div>
    </section>
    <div v-if="showModal" class="fixed inset-0 z-50 bg-black/70 flex items-center justify-center p-4">
      <div class="relative max-w-4xl w-full">
        <button class="absolute top-3 right-3 bg-white p-2 rounded-full shadow hover:bg-gray-200" @click="closeModal">
          <Icon icon="line-md:close" class="w-6 h-6 text-gray-700" />
        </button>
        <img :src="activeImage" class="w-full max-h-[90vh] object-contain rounded-lg" alt="Preview" />
      </div>
    </div>
    <section class="flex items-center justify-center">
      <div class="max-w-7xl mx-auto p-4">
        <div class="relative z-10">
          <div class="mb-8">
            <CarOverview />
          </div>
        </div>
      </div>
    </section>
     <div class="items-center mx-auto h-[1px] bg-gradient-to-r from-gray-300 via-gray-400 to-gray-300 my-8 max-w-7xl"></div>
    <section class="flex items-start justify-start max-w-7xl mx-auto p-4">
    <div class="mb-8 text-start">
      <h2 class="text-3xl font-bold text-gray-800 mb-2">Description</h2>
      <p class="text-start py-2 text-gray-600">
        Quisque imperdiet dignissim enim dictum finibus. Sed consectetutr convallis enim eget laoreet. Aenean vitae nisl mollis, porta risus vel, dapibus lectus. Etiam ac suscipit eros, eget maximus
      </p>
      <p class="text-start py-2 text-gray-600">
        Etiam sit amet ex pharetra, venenatis ante vehicula, gravida sapien. Fusce eleifend vulputate nibh, non cursus augue placerat pellentesque. Sed venenatis risus nec felis mollis, in pharetra urna euismod. Morbi aliquam ut turpis sit amet ultrices. Vestibulum mattis blandit nisl, et tristique elit scelerisque nec. Fusce eleifend laoreet dui eget aliquet. Ut rutrum risus et nunc pretium scelerisque.
      </p>
    </div>
    </section>
    <div class="items-center mx-auto h-[1px] bg-gradient-to-r from-gray-300 via-gray-400 to-gray-300 my-8 max-w-7xl"></div>
    <section class="flex items-start justify-start max-w-7xl mx-auto p-4">
          <div class="mb-8 text-start">
      <h2 class="text-3xl font-bold text-gray-800 mb-2">Features</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8 mt-6">
        <div>
          <h3 class="text-xl font-semibold text-gray-700 mb-4">Interior</h3>
          <ul class="space-y-2">
            <li class="flex items-center text-gray-600">
              <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Air Conditioner
            </li>
            <li class="flex items-center text-gray-600">
              <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Digital Odometer
            </li>
            <li class="flex items-center text-gray-600">
              <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Heater
            </li>
            <li class="flex items-center text-gray-600">
              <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Leather Seats
            </li>
            <li class="flex items-center text-gray-600">
              <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Panoramic Moonroof
            </li>
            <li class="flex items-center text-gray-600">
              <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Tachometer
            </li>
            <li class="flex items-center text-gray-600">
              <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Touchscreen Display
            </li>
          </ul>
        </div>
        <div>
          <h3 class="text-xl font-semibold text-gray-700 mb-4">Safety</h3>
          <ul class="space-y-2">
            <li class="flex items-center text-gray-600">
              <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Anti-lock Braking
            </li>
            <li class="flex items-center text-gray-600">
              <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Brake Assist
            </li>
            <li class="flex items-center text-gray-600">
              <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Child Safety Locks
            </li>
            <li class="flex items-center text-gray-600">
              <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Driver Air Bag
            </li>
            <li class="flex items-center text-gray-600">
              <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Power Door Locks
            </li>
            <li class="flex items-center text-gray-600">
              <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Stability Control
            </li>
            <li class="flex items-center text-gray-600">
              <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Traction Control
            </li>
          </ul>
        </div>
        <div>
          <h3 class="text-xl font-semibold text-gray-700 mb-4">Exterior</h3>
          <ul class="space-y-2">
            <li class="flex items-center text-gray-600">
              <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Fog Lights Front
            </li>
            <li class="flex items-center text-gray-600">
              <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Rain Sensing Wiper
            </li>
            <li class="flex items-center text-gray-600">
              <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Rear Spoiler
            </li>
            <li class="flex items-center text-gray-600">
              <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Windows - Electric
            </li>
          </ul>
        </div>
        <div>
          <h3 class="text-xl font-semibold text-gray-700 mb-4">Comfort & Convenience</h3>
          <ul class="space-y-2">
            <li class="flex items-center text-gray-600">
              <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Android Auto
            </li>
            <li class="flex items-center text-gray-600">
              <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Apple CarPlay
            </li>
            <li class="flex items-center text-gray-600">
              <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Bluetooth
            </li>
            <li class="flex items-center text-gray-600">
              <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> HomeLink
            </li>
            <li class="flex items-center text-gray-600">
              <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Power Steering
            </li>
            <li class="flex items-center text-gray-600">
              <Icon icon="mdi:check-circle" class="w-5 h-5 text-primary mr-2" /> Vanity Mirror
            </li>
          </ul>
        </div>
      </div>
    </div>
    </section>
    <div class="items-center mx-auto h-[1px] bg-gradient-to-r from-gray-300 via-gray-400 to-gray-300 my-8 max-w-7xl"></div>
    <section class="flex items-start justify-start max-w-7xl mx-auto p-4">
      <div class="mb-8 text-start w-full">
        <h2 class="text-3xl font-bold text-gray-800 mb-2">Dimensions & Capacity</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-x-16 gap-y-4 mt-6">
          <div class="flex justify-between">
            <span class="text-gray-600">Length</span>
            <span class="font-semibold text-gray-800">4550mm</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Width</span>
            <span class="font-semibold text-gray-800">2140mm</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Height</span>
            <span class="font-semibold text-gray-800">1550mm</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Width (including mirrors)</span>
            <span class="font-semibold text-gray-800">2140mm</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Wheelbase</span>
            <span class="font-semibold text-gray-800">2584mm</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Gross Vehicle Weight (kg)</span>
            <span class="font-semibold text-gray-800">1850</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Height (including roof rails)</span>
            <span class="font-semibold text-gray-800">1876mm</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Max. Loading Weight (kg)</span>
            <span class="font-semibold text-gray-800">1200</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Luggage Capacity (Seats Up - Litres)</span>
            <span class="font-semibold text-gray-800">350</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Max. Roof Load (kg)</span>
            <span class="font-semibold text-gray-800">350</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Luggage Capacity (Seats Down - Litres)</span>
            <span class="font-semibold text-gray-800">850</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">No. of Seats</span>
            <span class="font-semibold text-gray-800">5</span>
          </div>
        </div>
 <div class="items-center mx-auto h-[1px] bg-gradient-to-r from-gray-300 via-gray-400 to-gray-300 my-8 max-w-7xl"></div>
        <h2 class="text-3xl font-bold text-gray-800 mb-2 mt-12">Engine and Transmission</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-x-16 gap-y-4 mt-6">
          <div class="flex justify-between">
            <span class="text-gray-600">Fuel Tank Capacity (Litres)</span>
            <span class="font-semibold text-gray-800">85</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Minimum Kerbweight (kg)</span>
            <span class="font-semibold text-gray-800">350</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Max. Towing Weight - Braked (kg)</span>
            <span class="font-semibold text-gray-800">1000</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Turning Circle - Kerb to Kerb (m)</span>
            <span class="font-semibold text-gray-800">5000</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600">Max. Towing Weight - Unbraked (kg)</span>
            <span class="font-semibold text-gray-800">1200</span>
          </div>
        </div>
      </div>
    </section>
  <div class="max-w-4xl mx-auto bg-white shadow-lg rounded-2xl p-6">
    <h2 class="text-2xl font-semibold mb-4">Duty & Tax Calculator</h2>

    <form @submit.prevent="calculate" class="grid gap-4 md:grid-cols-2">
      <!-- Left column: inputs -->
      <div class="space-y-3">
        <label class="block">
          <span class="text-sm text-gray-600">Vehicle FOB / Purchase Price</span>
          <div class="flex items-center mt-1">
            <input v-model.number="fob"
                   type="number"
                   min="0"
                   step="0.01"
                   class="w-full rounded-md border px-3 py-2 focus:outline-none focus:ring"
                   placeholder="0.00" />
            <select v-model="currency" class="ml-2 rounded-md border px-2 py-2">
              <option value="USD">USD</option>
              <option value="BDT">BDT</option>
            </select>
          </div>
        </label>

        <label class="block">
          <span class="text-sm text-gray-600">Freight (shipping)</span>
          <input v-model.number="freight" type="number" min="0" step="0.01"
                 class="w-full rounded-md border px-3 py-2 focus:outline-none focus:ring" placeholder="0.00" />
        </label>

        <label class="block">
          <span class="text-sm text-gray-600">Insurance</span>
          <input v-model.number="insurance" type="number" min="0" step="0.01"
                 class="w-full rounded-md border px-3 py-2 focus:outline-none focus:ring" placeholder="0.00" />
        </label>

        <label class="block">
          <span class="text-sm text-gray-600">Other fees (inspection, clearance, port fees)</span>
          <input v-model.number="otherFees" type="number" min="0" step="0.01"
                 class="w-full rounded-md border px-3 py-2 focus:outline-none focus:ring" placeholder="0.00" />
        </label>

        <label class="block">
          <span class="text-sm text-gray-600">Exchange rate (1 USD = ? BDT)</span>
          <input v-model.number="exchangeRate" type="number" min="0" step="0.01"
                 class="w-full rounded-md border px-3 py-2 focus:outline-none focus:ring" placeholder="Example: 108.50" />
        </label>
      </div>

      <!-- Right column: rates & actions -->
      <div class="space-y-3">
        <p class="text-sm text-gray-600">Tax & Duty Rates (editable)</p>

        <label class="block">
          <span class="text-xs text-gray-500">Customs Duty (%)</span>
          <input v-model.number="rates.customs" type="number" min="0" step="0.01"
                 class="w-full rounded-md border px-3 py-2 focus:outline-none focus:ring" />
        </label>

        <label class="block">
          <span class="text-xs text-gray-500">VAT (%)</span>
          <input v-model.number="rates.vat" type="number" min="0" step="0.01"
                 class="w-full rounded-md border px-3 py-2 focus:outline-none focus:ring" />
        </label>

        <label class="block">
          <span class="text-xs text-gray-500">AIT (%)</span>
          <input v-model.number="rates.ait" type="number" min="0" step="0.01"
                 class="w-full rounded-md border px-3 py-2 focus:outline-none focus:ring" />
        </label>

        <div class="flex items-center gap-2 mt-4">
          <button type="submit"
                  class="px-4 py-2 rounded-lg bg-primary text-white hover:bg-primary-dark">
            Calculate
          </button>
          <button type="button" @click="reset"
                  class="px-4 py-2 rounded-lg border text-gray-700 hover:bg-gray-50">
            Reset
          </button>
          <button type="button" @click="copySummary"
                  class="ml-auto px-3 py-2 rounded-lg border text-gray-700 hover:bg-gray-50">
            Copy Summary
          </button>
        </div>

        <p class="text-xs text-gray-500 mt-2">
          Tip: adjust rates & exchange rate to match current regulation.
        </p>
      </div>
    </form>

    <!-- Divider -->
    <div class="my-5 h-px bg-gradient-to-r from-gray-200 via-gray-300 to-gray-200"></div>

    <!-- Results -->
    <div v-if="calculated" class="grid gap-3">
      <div class="flex justify-between items-center">
        <h3 class="text-lg font-medium">Breakdown</h3>
        <span class="text-sm text-gray-500">All amounts shown in <strong>{{ displayCurrency }}</strong></span>
      </div>

      <table class="w-full text-sm">
        <tbody>
          <tr class="border-b">
            <td class="py-2 text-gray-600">FOB</td>
            <td class="py-2 text-right font-medium">{{ fmt(displayed(fob)) }}</td>
          </tr>
          <tr class="border-b">
            <td class="py-2 text-gray-600">Freight</td>
            <td class="py-2 text-right">{{ fmt(displayed(freight)) }}</td>
          </tr>
          <tr class="border-b">
            <td class="py-2 text-gray-600">Insurance</td>
            <td class="py-2 text-right">{{ fmt(displayed(insurance)) }}</td>
          </tr>
          <tr class="border-b">
            <td class="py-2 text-gray-600">CIF (FOB + Freight + Insurance)</td>
            <td class="py-2 text-right font-medium">{{ fmt(displayed(cif)) }}</td>
          </tr>

          <tr class="border-b">
            <td class="py-2 text-gray-600">Customs Duty ({{ rates.customs }}%)</td>
            <td class="py-2 text-right">{{ fmt(displayed(customsDuty)) }}</td>
          </tr>

          <tr class="border-b">
            <td class="py-2 text-gray-600">VAT base (CIF + Customs)</td>
            <td class="py-2 text-right">{{ fmt(displayed(vatBase)) }}</td>
          </tr>

          <tr class="border-b">
            <td class="py-2 text-gray-600">VAT ({{ rates.vat }}%)</td>
            <td class="py-2 text-right">{{ fmt(displayed(vat)) }}</td>
          </tr>

          <tr class="border-b">
            <td class="py-2 text-gray-600">AIT ({{ rates.ait }}%)</td>
            <td class="py-2 text-right">{{ fmt(displayed(ait)) }}</td>
          </tr>

          <tr class="border-b">
            <td class="py-2 text-gray-600">Other fees</td>
            <td class="py-2 text-right">{{ fmt(displayed(otherFees)) }}</td>
          </tr>

          <tr>
            <td class="py-3 text-lg font-semibold">Total Payable</td>
            <td class="py-3 text-right text-lg font-semibold">{{ fmt(displayed(total)) }}</td>
          </tr>
        </tbody>
      </table>

      <div class="flex gap-3 mt-3 text-sm text-gray-600">
        <div>Exchange rate used: <strong>{{ exchangeRate }}</strong></div>
        <div class="ml-auto">Calculated at: <strong>{{ timestamp }}</strong></div>
      </div>
    </div>
  </div>
  </section>
</template>
