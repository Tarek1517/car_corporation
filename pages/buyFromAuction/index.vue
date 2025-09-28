<script setup>
import { ref, onMounted } from "vue";
import { Icon } from "@iconify/vue";

const isLoaded = ref(false);
onMounted(() => {
  isLoaded.value = true;
});

const activeTab = ref("services");

const tabs = [
  { key: "services", label: "Auction Services", icon: "mdi:car-multiple" },
  { key: "how", label: "How to Buy", icon: "mdi:cart-arrow-down" },
  { key: "calendar", label: "Auction Calendar", icon: "mdi:calendar-month" },
  { key: "terms", label: "Auction Terms", icon: "mdi:file-document-outline" },
  { key: "faq", label: "Auction FAQ", icon: "mdi:help-circle-outline" },
];
const features = [
  {
    icon: 'mdi-cash-multiple',
    title: 'Cheaper Prices',
    text: 'Japanese Car Auctions are best source of vehicles at low price, as they are sold at competitive price in Auctions.'
  },
  {
    icon: 'mdi-car-multiple',
    title: 'Wide Variety',
    text: 'Over 100,000 vehicles are available from all major auction halls in Japan to choose your preferred vehicle.'
  },
  {
    icon: 'mdi-magnify',
    title: 'Accuracy',
    text: 'Get accurate inspection sheet of vehicle from Auctions to get correct vehicle condition. We assure you high quality vehicles at best price.'
  },
  {
    icon: 'mdi-chart-line',
    title: 'Sales Statistics',
    text: 'Market Price Data of different vehicles is available to find out average price before you bid. Get Maximum Profit!!'
  },
  {
    icon: 'mdi-star-circle',
    title: 'Premium Quality',
    text: 'High Quality Used Vehicles are available at Japan Auto Auctions at average prices.'
  },
  {
    icon: 'mdi-truck-fast',
    title: 'Fast Shipment',
    text: 'We provide smooth custom clearance and fast shipment on next available vessel.'
  },
]

const auctions = ref([
  {
    date: '2023-06-15',
    auctionHouse: 'USS Tokyo',
    location: 'Tokyo, Japan',
    startTime: '09:00',
    endTime: '17:00',
    status: 'Completed'
  },
  {
    date: '2023-06-20',
    auctionHouse: 'TAA Kobe',
    location: 'Kobe, Japan',
    startTime: '10:00',
    endTime: '18:00',
    status: 'Completed'
  },
  {
    date: '2023-06-25',
    auctionHouse: 'USS Osaka',
    location: 'Osaka, Japan',
    startTime: '09:30',
    endTime: '17:30',
    status: 'Completed'
  },
  {
    date: '2023-07-05',
    auctionHouse: 'JU Fukuoka',
    location: 'Fukuoka, Japan',
    startTime: '09:00',
    endTime: '16:00',
    status: 'Upcoming'
  },
  {
    date: '2023-07-10',
    auctionHouse: 'USS Nagoya',
    location: 'Nagoya, Japan',
    startTime: '10:00',
    endTime: '18:00',
    status: 'Upcoming'
  }
]);
const deposites = ref([
  {
    price: 'Under BDT 1,000,000',
    desposit: 'BDT 100,000'
  },
  {
    price: 'BDT 1,010,000~1,500,000',
    desposit: 'BDT 200,000'
  },
  {
    price: 'BDT 1,510,000~2,000,000',
    desposit: 'BDT 300,000'
  },
  {
    price: 'Above BDT 2,010,000',
    desposit: 'BDT 500,000'
  },

]);
const getStatusClass = (status) => {
  if (status === 'Completed') return 'bg-red-100 text-red-800';
  if (status === 'Upcoming') return 'bg-blue-100 text-blue-800';
  if (status === 'Ongoing') return 'bg-green-100 text-green-800';
  return 'bg-gray-100 text-gray-800';
};

const formatDate = (dateString) => {
  const options = { year: 'numeric', month: 'short', day: 'numeric' };
  return new Date(dateString).toLocaleDateString(undefined, options);
};
const faqs = ref([
  {
    question: "Why buyers need to make a Deposit?",
    answer:
      "Your deposits are 100% Refundable. We require a deposit to ensure security of both the user and us that there will be no last minute cancellations of bid or any fake or spam bid request.In case the bid is failed and the car is sold to someone else, your deposit will be refunded or you can use the same in your next bidding.",
    open: false,
  },
  {
    question: "Is there a need for deposit to check vehicles in auction?",
    answer:
      "We grant you 100% free Registration and access to Japan car auctions, but to start bidding for your preferred car, a deposit is required depending on the total price of the car(s) that you want.",
    open: false,
  },
  {
    question: "How can I pay the deposit?",
    answer:
      "You can contact us for making the Deposit for the Auction bidding. We will issue a specific invoice of 1000$ for the deposit to be paid.",
    open: false,
  },
  {
    question: "What is the payment condition?",
    answer:
      "After the successful bid, please make full payment in 48 hours as per the invoice we will share with you in our Japan Bank Account. If payment is not made within 48 hours, the vehicle will be sold to another customer.",
    open: false,
  },
]);

const toggleFAQ = (index) => {
  faqs.value[index].open = !faqs.value[index].open;
};

onMounted(() => {
  setTimeout(() => {
    isLoaded.value = true;
  }, 100);
});
</script>

<template>
  <section
    class="w-full relative overflow-hidden">
    <div
      class="absolute top-0 right-0 w-96 h-96 bg-blue-500/10 rounded-full -translate-y-1/3 translate-x-1/3 blur-3xl animate-pulse-slow">
    </div>
    <div
      class="absolute bottom-0 left-0 w-[32rem] h-[32rem] bg-indigo-600/10 rounded-full translate-y-1/3 -translate-x-1/3 blur-3xl animate-pulse-slow delay-1000">
    </div>
    <div class="absolute top-1/2 left-1/4 w-64 h-64 bg-cyan-500/5 rounded-full blur-3xl animate-pulse-slow delay-500">
    </div>
    <div class="absolute inset-0 opacity-[0.05] bg-grid-pattern"></div>

    <div class="relative z-10">
      <section class="relative">
        <div class="relative h-[600px] md:h-[500px] w-full overflow-hidden">
          <img src="../../public/images/car-auction.jpg" alt=""
            class="w-full h-full object-cover scale-105 transform transition-transform duration-10000 hover:scale-110" />
          <div class="absolute inset-0 flex flex-col items-end justify-center text-right z-10 max-w-7xl mx-auto">
            <div
              class="mb-4 px-3 py-1 bg-red-500/20 backdrop-blur-sm rounded-full border border-red-400/30 text-gray-100 text-sm font-medium animate-fade-in-down">
              PREMIUM AUCTIONS SINCE 2010
            </div>

            <h2 class="text-5xl md:text-7xl font-bold text-white mb-4 drop-shadow-lg transition-all duration-1000"
              :class="isLoaded
                ? 'translate-y-0 opacity-100'
                : 'translate-y-10 opacity-0'
                ">
              Buy From
              <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">
                Car Auctions
              </span>
            </h2>

            <p class="text-xl md:text-2xl text-gray-200 max-w-2xl drop-shadow-md mb-8 transition-all duration-1000 delay-300"
              :class="isLoaded
                ? 'translate-y-0 opacity-100'
                : 'translate-y-10 opacity-0'
                ">
              Discover exceptional vehicles at our exclusive auctions. With
              transparent bidding, expert inspections, and a passion for
              automotive excellence, we bring you the finest cars at competitive
              prices.
            </p>

          </div>

          <div class="absolute bottom-0 left-0 w-full h-24 bg-gradient-to-b from-transparent via-black/20 to-black/40">
          </div>

          <div class="absolute bottom-6 left-6 flex items-center gap-2 text-white/80 text-sm">
            <Icon icon="mdi:calendar-clock" class="w-4 h-4" />
            <span>Next Auction: June 15, 6PM</span>
          </div>
        </div>
      </section>

      <section class="bg-white py-4">
        <div class="max-w-[8000px] mx-auto px-4">
          <div class="flex flex-wrap justify-center gap-2 md:gap-4 mb-8">
            <button v-for="tab in tabs" :key="tab.key" @click="activeTab = tab.key"
              class="group relative flex items-center justify-center px-4 py-3 md:px-6 md:py-4 rounded-xl transition-all duration-300 transform hover:-translate-y-1 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-primary overflow-hidden"
              :class="[
                activeTab === tab.key
                  ? 'bg-gradient-to-r from-primary to-secondary text-white shadow-lg'
                  : 'bg-gray-100 text-gray-700 hover:bg-gray-200'
              ]">
              <span
                class="absolute inset-0 rounded-xl bg-gradient-to-r from-primary to-secondary opacity-0 group-hover:opacity-10 transition-opacity duration-300"
                :class="{ 'opacity-0': activeTab === tab.key }"></span>
              <Icon :icon="tab.icon"
                class="w-5 h-5 md:w-6 md:h-6 mr-2 transition-transform duration-300 group-hover:scale-110"
                :class="activeTab === tab.key ? 'text-white' : 'text-primary'" />

              <span class="font-medium text-sm md:text-base">{{ tab.label }}</span>

              <span v-if="activeTab === tab.key"
                class="absolute -bottom-1 left-1/2 transform -translate-x-1/2 w-1.5 h-1.5 bg-white rounded-full"></span>
            </button>
          </div>

          <div v-if="activeTab === 'services'">
            <div class="mx-auto px-4 md:px-6 max-w-7xl relative z-10">
              <div class="text-center mb-12">
                <h1 class="text-3xl md:text-4xl font-bold text-gray-800 mb-4">
                  Auction Service
                </h1>
              </div>
              <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                <div class="text-left">
                  <h1 class="text-xl md:text-2xl lg:text-3xl font-bold text-gray-900 leading-tight mb-6">
                    Start Accessing over
                    <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">100,000 Cars
                      at Japan Auto Auction!</span>
                  </h1>

                  <p class="text-md text-gray-600 mb-8 max-w-xl">
                    Get Access to all major Japan Cars Auctions with over 100,000 vehicles updated weekly.
                    Find your prefered cars at our user friendly Japan Auto Auctions search engine. Our trained experts
                    are always happy to assist you to allocate your budget and buy vehicles from Auction at best price.
                  </p>
                  <div class="flex flex-wrap gap-4">
                    <button
                      class="px-8 py-4 bg-gradient-to-r from-primary to-secondary text-white rounded-xl font-semibold shadow-lg hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1 flex items-center">
                      <span class="uppercase">Contact Us To Get Auction Access</span>
                    </button>
                  </div>
                </div>

                <div class="relative">
                  <div class="rounded-2xl overflow-hidden shadow-2xl">
                    <img src="../../public/images/car-service-aution.png" alt="Premium Japanese Vehicle"
                      class="w-full h-auto object-cover" />
                  </div>
                </div>
              </div>
            </div>
            <section class="w-full py-16 bg-white">
              <div class="text-center mb-16">
                <h2 class="text-2xl md:text-3xl font-bold text-gray-900 mb-4">
                  Why Buy Cars <span class="text-primary">from Japan</span> Auto Auctions?
                </h2>
              </div>
              <div class="max-w-6xl mx-auto grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 px-4">
                <div v-for="(item, index) in features" :key="index"
                  class="text-center px-6 py-10 border border-gray-200">
                  <Icon :icon="item.icon" class="text-red-500 text-5xl mb-4 mx-auto" />
                  <h3 class="font-bold text-gray-700 text-lg mb-2 uppercase">{{ item.title }}</h3>
                  <p class="text-gray-700 text-sm leading-relaxed">
                    {{ item.text }}
                  </p>
                </div>
              </div>
            </section>
          </div>

          <div v-else-if="activeTab === 'how'">
            <div class="mx-auto px-4 md:px-6 max-w-7xl relative z-10">
              <div class="text-center mb-12">
                <h1 class="text-3xl md:text-4xl font-bold text-gray-800 mb-4">
                  How to Buy from Auction
                </h1>
              </div>
              <div class="mx-auto relative z-10">
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                  <div class="space-y-4 mx-auto">
                    <div class="flex items-start bg-white p-6 rounded-2xl shadow-lg border border-gray-200/80">
                      <div class="flex-shrink-0 w-28 h-28 bg-gray-200 rounded-xl flex items-center justify-center mr-6">
                        <span class="text-gray-500 text-4xl font-bold text-center">STEP 1</span>
                      </div>
                      <div class="flex-grow">
                        <h3
                          class="text-xl font-semibold text-gray-800 mb-2 bg-gray-200 px-4 py-2 rounded-full inline-block">
                          Advance Deposit
                        </h3>
                        <p class="text-gray-600 leading-relaxed">
                          Make an advance deposit to bid for the vehicle you want to buy from the auction. The deposit
                          amount will depend on the price of the vehicle as mentioned in the table below.
                        </p>
                      </div>
                    </div>
                    <div class="overflow-x-auto bg-white shadow-lg">
                      <table class="min-w-full divide-y divide-gray-200">
                        <thead class="bg-gray-50">
                          <tr>
                            <th scope="col"
                              class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                              Car Price
                            </th>
                            <th scope="col"
                              class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                              Deposit
                            </th>
                          </tr>
                        </thead>
                        <tbody class="bg-white divide-y divide-gray-200">
                          <tr v-for="(deposit, index) in deposites" :key="index" class="hover:bg-gray-50">
                            <td class="px-4 py-4 whitespace-nowrap text-sm text-gray-500">{{ deposit.price }}</td>
                            <td class="px-4 py-4 whitespace-nowrap text-sm text-gray-500">{{ deposit.desposit }}</td>
                          </tr>
                        </tbody>
                      </table>
                      <div v-if="deposites.length === 0" class="text-center py-8 text-gray-500">
                        No deposit information available.
                      </div>
                    </div>
                  </div>
                  <div class="relative">
                    <div class="rounded-2xl overflow-hidden shadow-2xl">
                      <img src="../../public/images/table.png" alt="Premium Japanese Vehicle"
                        class="w-[600px] h-[500px] object-fit" />
                    </div>
                  </div>
                </div>
              </div>
              <div class="mx-auto relative z-10">
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                  <div class="relative">
                    <div class="rounded-2xl overflow-hidden shadow-2xl">
                      <img src="../../public/images/table.png" alt="Premium Japanese Vehicle"
                        class="w-full h-full object-cover" />
                    </div>
                  </div>
                  <div class="space-y-4 mx-auto">
                    <div class="flex items-start bg-white p-6 rounded-2xl shadow-lg border border-gray-200/80">
                      <div class="flex-shrink-0 w-28 h-28 bg-gray-200 rounded-xl flex items-center justify-center mr-6">
                        <span class="text-gray-500 text-4xl font-bold text-center">STEP 2</span>
                      </div>
                      <div class="flex-grow">
                        <h3
                          class="text-xl font-semibold text-gray-800 mb-2 bg-gray-200 px-4 py-2 rounded-full inline-block">
                          Make Bid for your Preferred Vehicle
                        </h3>
                        <p class="text-gray-600 leading-relaxed">

                          Make Bid for your Preferred Vehicle
                          Choose your required vehicle from our auction stock list and place the Bid using the Make Bid
                          form. We will receive your bid request and will make the bid in the Auction on your behalf.
                        </p>
                      </div>
                    </div>
                  </div>

                </div>
              </div>
              <div class="mx-auto relative z-10 py-12">
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                  <div class="space-y-4 mx-auto">
                    <div class="flex items-start bg-white p-6 rounded-2xl shadow-lg border border-gray-200/80">
                      <div class="flex-shrink-0 w-28 h-28 bg-gray-200 rounded-xl flex items-center justify-center mr-6">
                        <span class="text-gray-500 text-4xl font-bold text-center">STEP 3</span>
                      </div>
                      <div class="flex-grow">
                        <h3
                          class="text-xl font-semibold text-gray-800 mb-2 bg-gray-200 px-4 py-2 rounded-full inline-block">
                          Final Payment
                        </h3>
                        <p class="text-gray-600 leading-relaxed">
                          You can transfer the balance amount within 3 days from receiving the invoice in our Japan Bank
                          Account. Please provide us the Bank transfer slip as a proof of payment.
                        </p>
                      </div>
                    </div>
                  </div>
                  <div class="relative">
                    <div class="rounded-2xl overflow-hidden shadow-2xl">
                      <img src="../../public/images/finalpayment.png" alt="Premium Japanese Vehicle"
                        class="w-full h-full object-cover" />
                    </div>
                  </div>
                </div>
              </div>
              <div class="mx-auto relative z-10 py-12">
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                  <div class="relative">
                    <div class="rounded-2xl overflow-hidden shadow-2xl">
                      <img src="../../public/images/shipment.jpg" alt="" class="w-full h-full object-cover" />
                    </div>
                  </div>
                  <div class="space-y-4 mx-auto">
                    <div class="flex items-start bg-white p-6 rounded-2xl shadow-lg border border-gray-200/80">
                      <div class="flex-shrink-0 w-28 h-28 bg-gray-200 rounded-xl flex items-center justify-center mr-6">
                        <span class="text-gray-500 text-4xl font-bold text-center">STEP 4</span>
                      </div>
                      <div class="flex-grow">
                        <h3
                          class="text-xl font-semibold text-gray-800 mb-2 bg-gray-200 px-4 py-2 rounded-full inline-block">
                          Final Payment
                        </h3>
                        <p class="text-gray-600 leading-relaxed">
                          You can transfer the balance amount within 3 days from receiving the invoice in our Japan Bank
                          Account. Please provide us the Bank transfer slip as a proof of payment.
                        </p>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
              <div class="mx-auto relative z-10 py-12">
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                  <div class="space-y-4 mx-auto">
                    <div class="flex items-start bg-white p-6 rounded-2xl shadow-lg border border-gray-200/80">
                      <div class="flex-shrink-0 w-28 h-28 bg-gray-200 rounded-xl flex items-center justify-center mr-6">
                        <span class="text-gray-500 text-4xl font-bold text-center">STEP 5</span>
                      </div>
                      <div class="flex-grow">
                        <h3
                          class="text-xl font-semibold text-gray-800 mb-2 bg-gray-200 px-4 py-2 rounded-full inline-block">
                          Receive your Vehicle
                        </h3>
                        <p class="text-gray-600 leading-relaxed">
                          Once you receive the documents, you can collect and register the vehicle in your country. A
                          clearing agent can help you to complete the procedure and give you an indication on the fee
                          and taxes to be paid. Complete the procedures and enjoy your New Vehicle.
                        </p>
                      </div>
                    </div>
                  </div>
                  <div class="relative">
                    <div class="rounded-2xl overflow-hidden shadow-2xl">
                      <img src="../../public/images/finalpayment.png" alt="Premium Japanese Vehicle"
                        class="w-full h-full object-cover" />
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <div v-else-if="activeTab === 'calendar'">
            <section
              class="w-full relative overflow-hidden py-2 md:py-6 bg-gradient-to-br from-slate-50 via-white to-slate-100">
              <div class="container mx-auto px-4 relative">
                  <h2 class="text-4xl font-bold text-center mb-8 text-gray-800">Upcoming Auction Events</h2>
                <div class="px-1 py-8">

                  <div class="overflow-x-auto bg-white rounded-xl shadow-lg max-w-7xl">
                    <table class="min-w-full divide-y divide-gray-200">
                      <thead class="bg-gray-50">
                        <tr>
                          <th scope="col"
                            class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Date
                          </th>
                          <th scope="col"
                            class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                            Auction House</th>
                          <th scope="col"
                            class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                            Location</th>
                          <th scope="col"
                            class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Start
                            Time</th>
                          <th scope="col"
                            class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">End
                            Time</th>
                          <th scope="col"
                            class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                            Status</th>
                        </tr>
                      </thead>
                      <tbody class="bg-white divide-y divide-gray-200">
                        <tr v-for="(auction, index) in auctions" :key="index" class="hover:bg-gray-50">
                          <td class="px-4 py-4 whitespace-nowrap text-sm font-medium text-gray-900">
                            {{ formatDate(auction.date) }}
                          </td>
                          <td class="px-4 py-4 text-sm text-gray-900">{{ auction.auctionHouse }}</td>
                          <td class="px-4 py-4 whitespace-nowrap text-sm text-gray-500">{{ auction.location }}</td>
                          <td class="px-4 py-4 whitespace-nowrap text-sm text-gray-500">{{ auction.startTime }}</td>
                          <td class="px-4 py-4 whitespace-nowrap text-sm text-gray-500">{{ auction.endTime }}</td>
                          <td class="px-4 py-4 whitespace-nowrap">
                            <span class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full"
                              :class="getStatusClass(auction.status)">
                              {{ auction.status }}
                            </span>
                          </td>
                        </tr>
                      </tbody>
                    </table>
                    <div v-if="auctions.length === 0" class="text-center py-8 text-gray-500">
                      No upcoming auctions scheduled.
                    </div>
                  </div>
                </div>
              </div>
            </section>
          </div>

          <div v-else-if="activeTab === 'terms'">
            <div class="relative z-10 max-w-7xl mx-auto">
              <div class="px-1 py-4">
                              <div class="text-center mb-12">
                <h1 class="text-3xl md:text-4xl font-bold text-gray-800 mb-4">
                  Auction Terms
                </h1>
              </div>
                <h2 class="text-2xl font-bold text-start mb-8 text-gray-600">Auction Membership Registration</h2>
                <p class="text-md text-gray-600 mb-8 max-w-xl">
                  We provide Free Access to clients registered on our website for browsing vehicles available in Japan
                  Auto Auctions.
                  Auction Membership Registration is Free of cost, now Sign up & get access to more than 100,000 stock
                  in Auctions. Your information is safe with us and it is only used for Invoices and documentation
                  required in vehicle export. Client information in never disclosed to any other sources.
                </p>
              </div>
              <div class="px-1 py-2 max-w-xl">
                <h2 class="text-2xl font-bold text-start mb-4 text-gray-600">Advance Deposit</h2>
                <p class="text-md text-gray-600 mb-6 max-w-xl">
                  Advance deposit is required before bidding any vehicle in Japan Car Auctions depending upon the price
                  of the vehicle.
                </p>

                <div class="overflow-x-auto bg-white rounded-xl shadow-lg">
                  <table class="min-w-full divide-y divide-gray-200">
                    <thead class="bg-gray-50">
                      <tr>
                        <th scope="col"
                          class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                          Car Price
                        </th>
                        <th scope="col"
                          class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                          Deposit
                        </th>
                      </tr>
                    </thead>
                    <tbody class="bg-white divide-y divide-gray-200">
                      <tr v-for="(deposit, index) in deposites" :key="index" class="hover:bg-gray-50">
                        <td class="px-4 py-4 whitespace-nowrap text-sm text-gray-500">{{ deposit.price }}</td>
                        <td class="px-4 py-4 whitespace-nowrap text-sm text-gray-500">{{ deposit.desposit }}</td>
                      </tr>
                    </tbody>
                  </table>
                  <div v-if="deposites.length === 0" class="text-center py-8 text-gray-500">
                    No deposit information available.
                  </div>
                </div>
              </div>
              <div class="px-1 py-2 max-w-2xl">
                <h2 class="text-xl font-bold text-start mb-4 text-gray-600">Deposit is refundable anytime before the
                  bidding is succeeded.</h2>
                <li class="text-sm font-normal text-start text-gray-400">
                  Bank charges on both side will be deducted.
                </li>
              </div>
              <div class="px-1 py-2 max-w-2xl">
                <h2 class="text-xl font-bold text-start mb-2 text-gray-700">Note :</h2>
                <li class="text-sm font-normal text-start text-gray-400">To buy any vehicle from auction, please send
                  deposit US$1000, before any bidding.</li>
                <li class="text-sm font-normal text-start text-gray-400">All payments to be made in our Japan Bank
                  Account only.</li>
                <li class="text-sm font-normal text-start text-gray-400">Other charges may also apply on customer
                  demand.
                  - Inspection (JAVIC, JAAI, EAA).
                  - Packing Charges for container.</li>
                <li class="text-sm font-normal text-start text-gray-400">If for any reason you want to cancel the car
                  after the successful auction bidding, cancellation fees applies a fine of deposit according to above
                  table.</li>
              </div>
            </div>
          </div>

          <div v-else-if="activeTab === 'faq'">
            <section class="relative w-full py-12">
              <div class="container mx-auto px-4">
                <h2 class="text-3xl md:text-4xl font-bold text-center text-gray-800 mb-10">
                  Auction FAQ
                </h2>

                <div class="max-w-full mx-auto space-y-4">
                  <div v-for="(faq, index) in faqs" :key="index"
                    class="border rounded-2xl overflow-hidden shadow-sm bg-white">
                    <button
                      class="w-full flex justify-between items-center px-6 py-4 text-left text-gray-800 font-medium hover:bg-gray-50 transition"
                      @click="toggleFAQ(index)">
                      <span>{{ faq.question }}</span>
                      <Icon icon="mdi:chevron-down"
                        class="w-6 h-6 text-gray-600 transform transition-transform duration-300"
                        :class="{ 'rotate-180': faq.open }" />
                    </button>

                    <div v-show="faq.open" class="px-6 pb-4 text-gray-600 animate-fade-in">
                      {{ faq.answer }}
                    </div>
                  </div>
                </div>
              </div>
            </section>
          </div>
        </div>
      </section>
    </div>
  </section>
</template>

<style scoped>
@keyframes fade-in-down {
  0% {
    opacity: 0;
    transform: translateY(-20px);
  }

  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in-down {
  animation: fade-in-down 0.8s ease-out forwards;
}

@keyframes pulse-slow {

  0%,
  100% {
    opacity: 0.2;
  }

  50% {
    opacity: 0.4;
  }
}

.animate-pulse-slow {
  animation: pulse-slow 4s cubic-bezier(0.4, 0, 0.6, 1) infinite;
}

.delay-500 {
  animation-delay: 0.5s;
}

.delay-1000 {
  animation-delay: 1s;
}
</style>
