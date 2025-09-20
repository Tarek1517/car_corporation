<script setup>
import { ref } from "vue";
import { Icon } from "@iconify/vue";
const faqs = ref([
    {
        question: "Why Pre-Order?",
        answer: "We directly collect the vehicles from the various auctions in Japan and arrange the shipment procedure to hand over your dream car in your hand as it is without any change. We don’t let our clients face any hassles of buying from Japanese Auction House till get the delivery to their door steps.For any purchase, most importantly, the prices of different sources are compared. But the value should not be ignored. For understanding the value of a car many other factors, specially the conditions, have to be known in details. Because the price of a known condition car cannot be compare with the price of a car with unknown condition. FAIR AUTOMOBILES provide you only the known-condition car. Before compare the price, compare the condition and life-time value. Paying higher for better value is buying intelligence. FAIR AUTOMOBILES is the price leader for the car in comparison to cars of same grade and condition. You will never lose by purchasing with us. In a conventional reconditioned car market, when a deal is completed either the buyer win or lose. For an opened-eyed-blind (less informed) buyer who rely on appearance but not real condition, always, there is a high possibility of being loser during the trans or even long after the transaction while using the car.",
        open: false,
    },
    {
        question: "Why Choose Us?",
        answer: "You choose the car & price; we’ll import it for you! With thousands of cars at auction everyday in Japan, you can bid on as many as you like! Inform us your maximum landed price and we will bid up to that amount. If we can get the car cheaper, that is all you will pay! We arrange everything involved in getting the car from the auction house in Japan to Bangladesh. We have negotiated discounted rates on shipping and compliance costs enabling our customers to save hundreds.We bid and buy on your behalf and secure it for the best possible price. We arrange everything required to have the car on road in Bangladesh We guarantee the condition of all cars as they are carefully inspected for you, if it arrives and is not in the condition described we will sort it or refund your purchase price.",
        open: false,
    },
    {
        question: "Our Guarantee",
        answer: "FAIR AUTOMOBILES carries all the risks out of purchasing and importing a vehicle direct from auction houses located in Japan. We provide guarantees so you can be sure that you are getting exactly what you pay for. There will be no cost escalation by surprising you with claims of hidden spending requirements. Every vehicle, on Japanese auction, is professionally and independently inspected. The results and findings are published alongside the vehicle’s photos in the auction report. GUARANTEED BEST PRICE: FAIR AUTOMOBILES never profits from the auction process. We are mainly logistics providers. So our job is to get the right vehicle for you at the lowest price. We provide the Best Price ideas by informing the price trends of the car of certain brand and condition/grade. We come to know from you the maximum limit of bidding price for the car of your choice. If we can make you a winner, we provide you the original auction invoice of the vehicle. If the winning auction price is less than your maximum limit, all the savings are yours. You can be sure about the price from many other web sites those host the information of Japanese auctions. And you can easily match the auction price and chassis numbers on the invoice and the auction data. Anyone can import vehicle through FAIR AUTOMOBILES and it will be the same price for all individual. GUARANTEED CONDITION: All vehicles, bought through FAIR AUTOMOBILES, are guaranteed to be in the condition described at the time of auction. Each vehicle’s condition and its operation are checked before departure. Any vehicle found to have undisclosed damage or faults is returned to the auction house (there is a 5 day claim period for Japanese Auctions). In such cases, the transaction will be void and you will not be charged anything for the cancelled deal. We shall initiate another fresh bidding for you. CERTIFICATE: All vehicles, bought through FAIR AUTOMOBILES, are inspected and issued JAAI (Japan Auto Appraisal Institute) certificate. Each vehicle has to do its odometer verification tests from Japan. After the test, the original mileage is declared which you can check & match at the moment of taking over of your vehicle. GUARANTEED COMPLIANCE: FAIR AUTOMOBILES professional auction team has a thorough knowledge of local import and export regulations. FAIR AUTOMOBILES provide 100% guarantees that any vehicle purchased through us is fully compliant with Bangladesh regulation of import as well as rules of Bangladesh Roads & Transport Authority (BRTA). We can claim a 100% refund if the vehicle you purchase through FAIR AUTOMOBILES fail to comply the above rules and regulations.",
        open: false,
    },
    {
        question: "Pre-Order Terms & Conditions",
        answer: "1. When you confirm participating in bid you will need to provide security deposit of Tk. 1,00,000 (One Lac). This security deposit will be a part-payment of the total price of your vehicle. 2. FAIR AUTOMOBILES will notify you immediately (at the day of auction) if bid is won. The invoice for first installment (at least 30% of the total estimated price) will be issued in the following day. The invoice will mention the estimated landed cost in Bangladesh. The first installment has to be paid within 3 days of issuing the invoice. FAIR AUTOMOBILES reserve the right to re-auction of any vehicles due to failure of paying the first installment within the stipulated time. FAIR AUTOMOBILES also reserve the rights to adjust or forbid the security deposit for bearing the costs incurred in re-auction or reselling of the vehicle won in the auction. 3. The total landed costs to Bangladesh will be estimated based on the available information and rational forecast (It is still tentative, because the conversion of JPY & US$ to BDT is changing every day). We will provide the total offer letter to you to work on your side for arranging the rest of the payment or processing for the bank loan, if needed. 4. Finally FAIR AUTOMOBILES will provide you actual cost of landing in Bangladesh after clearing from the port. 5. Second installment (rest of the amount to meet the total cost after adjustment of security deposit and 1st installment) is needed prior to handover the vehicle to you. The number plate registration from BRTA will be provided as voluntary service to you at actual cost. 6. In the cases, we receive two or more bids for the same vehicle only the highest bid will be considered by FAIR AUTOMOBILES. If bids are the same then only the first bid will be considered. 7. Once a bid has been confirmed by you and a security deposit is paid, cancellation of the bid is not possible. 8. Modified, non-moving & huge repaired vehicles will not be considered for bidding through FAIR AUTOMOBILES.",
        open: false,
    },
]);

const toggleFAQ = (index) => {
    faqs.value[index].open = !faqs.value[index].open;
};
</script>
<template>
    <section
        class="w-full relative overflow-hidden py-2 md:py-6 bg-gradient-to-br from-slate-900 via-slate-800 to-slate-900">
        <div
            class="absolute top-0 right-0 w-96 h-96 bg-blue-500/10 rounded-full -translate-y-1/3 translate-x-1/3 blur-3xl animate-pulse-slow">
        </div>
        <div
            class="absolute bottom-0 left-0 w-[32rem] h-[32rem] bg-indigo-600/10 rounded-full translate-y-1/3 -translate-x-1/3 blur-3xl animate-pulse-slow delay-1000">
        </div>
        <div
            class="absolute top-1/2 left-1/4 w-64 h-64 bg-cyan-500/5 rounded-full blur-3xl animate-pulse-slow delay-500">
        </div>
        <div class="absolute inset-0 opacity-[0.05] bg-grid-pattern"></div>
        <div class="max-w-7xl mx-auto px-6 py-12 grid grid-cols-1 md:grid-cols-2 items-center gap-6">
            <div class="text-left text-white space-y-4">
                <h1 class="text-3xl md:text-4xl font-bold uppercase">
                    Order a Japanese Vehicle
                </h1>
                <p class="text-gray-300 max-w-md">
                    If you want to Pre-Order a vehicle, Please fill in the form below,
                    One of our representatives will contact you shortly.
                </p>
            </div>
            <div class="flex justify-center md:justify-end">
                <img src="../../public/images/honda-suv.png" alt="Japanese Car"
                    class="w-full max-w-md drop-shadow-xl" />
            </div>
        </div>
        <section class="relative w-full py-12 bg-gradient-to-br from-slate-50 via-white to-slate-100">
            <div class="container mx-auto p-4 py-4">
                <h1 class="text-3xl font-bold mb-4 text-gray-700">How to Pre-Order – Terms & Conditions</h1>

                <p class="mb-4 text-gray-700">1. A security deposit of Tk. 1,00,000 is required to confirm your
                    participation in bidding. This deposit is part of your final payment.</p>

                <p class="mb-4 text-gray-700">2. If you win the auction, a minimum of 30% of the estimated landed cost
                    must be paid within 3 working days of invoice issue.</p>

                <p class="mb-4 text-gray-700">3. The final installment (remaining balance) must be cleared before
                    vehicle delivery. BRTA registration can be arranged at actual cost.</p>

                <p class="mb-4 text-gray-700">4. If you fail to pay on time, the company reserves the right to
                    re-auction the vehicle and adjust your deposit.</p>

                <p class="mb-4 text-gray-700">5. Estimated costs may vary depending on foreign exchange rates and
                    shipping charges. Final costs are confirmed upon clearance at port.</p>

                <p class="mb-4 text-gray-700">6. Once a bid is confirmed, cancellation is not allowed.</p>
            </div>
                        <div class="container mx-auto px-4">
                <h2 class="text-3xl font-bold text-start text-gray-700 mb-10">
                    Frequently Asked Questions
                </h2>

                <div class="max-w-full mx-auto space-y-4">
                    <div v-for="(faq, index) in faqs" :key="index"
                        class="border rounded-2xl overflow-hidden shadow-sm bg-white">
                        <button
                            class="w-full flex justify-between items-center px-6 py-4 text-left text-gray-800 font-medium hover:bg-gray-50 transition"
                            @click="toggleFAQ(index)">
                            <span>{{ faq.question }}</span>
                            <Icon icon="mdi:plus"
                                class="w-6 h-6 text-gray-600 transform transition-transform duration-300"
                                :class="{ 'rotate-180': faq.open }" />
                        </button>

                        <!-- Answer -->
                        <div v-show="faq.open" class="px-6 pb-4 text-gray-600 animate-fade-in">
                            {{ faq.answer }}
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </section>
</template>