<script setup>
import { ref } from 'vue';
import { Icon } from '@iconify/vue';
const author = {
    name: 'Car Corporation Team',
    avatar: '/images/avater1.png',
    bio: 'Leading experts in importing Japanese cars to Bangladesh with over 10 years of experience in auctions, shipping, inspections, and BRTA registration services.'
};
const publishDate = new Date('2024-09-01');
const readTime = '8 min read';

const tocItems = [
    { id: 'research', title: '1. Research Bangladesh Import Regulations' },
    { id: 'sourcing', title: '2. Sourcing JDM Vehicles from Japan' },
    { id: 'documentation', title: '3. Prepare Essential Documentation' },
    { id: 'shipping', title: '4. Arrange International Shipping' },
    { id: 'customs', title: '5. Clear Customs with NBR' },
    { id: 'modifications', title: '6. Make Required Modifications' },
    { id: 'registration', title: '7. Register with BRTA' }
];

const relatedArticles = [
    {
        title: 'Guide to Japanese Car Auctions in Bangladesh',
        url: '/blogs/japan-auctions-guide'
    },
    {
        title: 'Understanding Import Duties and Taxes in Bangladesh',
        url: '/services/import-duties'
    },
    {
        title: 'Top Reconditioned Vehicles Available Now',
        url: '/reconditionedVehicles'
    }
];

const email = ref('');

const subscribeToNewsletter = () => {
    alert(`Thank you for subscribing with: ${email.value}! Stay updated on the latest car imports to Bangladesh.`);
    email.value = '';
};

// const shareOnFacebook = () => {
//   const url = window.location.href;
//   window.open(`https://www.facebook.com/sharer/sharer.php?u=${encodeURIComponent(url)}`, '_blank');
// };

const comments = ref([
    {
        id: 1,
        author: 'Rahim Khan',
        date: new Date('2024-09-05'),
        content: 'Excellent guide! I used Car Corporation for my Toyota Noah import from Japan auction. The shipping and customs process was seamless thanks to their team.',
        avatar: '/images/avater2.png'
    },
    {
        id: 2,
        author: 'Ayesha Rahman',
        date: new Date('2024-09-08'),
        content: 'This helped me avoid common pitfalls with BRTA registration. Highly recommend their inspection services for JDM cars!',
        avatar: '/images/avater3.png'
    }
]);

const newComment = ref({
    author: '',
    email: '',
    content: ''
});

const submitComment = () => {
    if (newComment.value.author && newComment.value.email && newComment.value.content) {
        comments.value.push({
            id: comments.value.length + 1,
            author: newComment.value.author,
            date: new Date(),
            content: newComment.value.content,
            avatar: '/images/default-avatar.png'
        });

        newComment.value = {
            author: '',
            email: '',
            content: ''
        };

        alert('Your comment has been submitted! We\'ll review it for our Bangladesh car import community.');
    } else {
        alert('Please fill in all fields');
    }
};
</script>

<template>
    <div class="min-h-screen bg-gray-50">
        <section class="relative overflow-hidden">
            <img src="/images/blog1.jpg" alt="How to Import Your Dream Car Easily to Bangladesh"
                class="w-full h-full md:h-96 object-cover" />
            <div class="absolute inset-0 bg-black/20 flex items-center justify-center">
                <div class="text-center text-white px-4">
                    <h1 class="text-3xl md:text-5xl font-bold mb-2">
                        How to Import <span
                            class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">Your Dream
                            <br> Car Easily</span> to Bangladesh
                    </h1>
                    <p class="text-lg opacity-90">A comprehensive guide for importing JDM vehicles from Japan auctions
                        with Car Corporation's expert support</p>
                </div>
            </div>
        </section>

        <div class="max-w-7xl mx-auto px-4 py-8">
            <div class="flex flex-col lg:flex-row gap-8">
                <article class="flex-1">
                    <div class="flex items-center justify-between mb-6 text-sm text-gray-500">
                        <div class="flex items-center gap-2">
                            <img :src="author.avatar" :alt="author.name" class="w-8 h-8 rounded-full text-gray-600" />
                            <span>By {{ author.name }}</span>
                        </div>
                        <div class="flex items-center gap-4">
                            <span>Published: {{ publishDate.toLocaleDateString() }}</span>
                            <span>{{ readTime }}</span>
                        </div>
                    </div>

                    <div class="text-gray-700 text-lg max-w-none">
                        <p class="text-gray-700 leading-relaxed mb-6">
                            Importing your dream car to Bangladesh has become increasingly popular, especially for
                            high-quality Japanese Domestic Market (JDM) vehicles like Toyota, Honda, and Nissan models.
                            At Car Corporation, we specialize in making this process hassle-free through our end-to-end
                            services including auctions, shipping, customs clearance, and reconditioning. This guide
                            outlines the key steps, tailored for Bangladeshi importers.
                        </p>

                        <h2 id="research">1. Research Bangladesh Import Regulations</h2>
                        <p>
                            Start by familiarizing yourself with Bangladesh's import rules governed by the National
                            Board of Revenue (NBR) and Bangladesh Road Transport Authority (BRTA). Key considerations
                            include:
                        </p>
                        <ul class="list-disc ml-6 mb-6">
                            <li>Vehicle age: Generally, cars must be under 3 years for personal imports or 5 years via
                                commercial schemes; older classics may qualify under special provisions.</li>
                            <li>Emission standards: Must meet Euro 4 or equivalent; JDM cars often need upgrades.</li>
                            <li>Right-hand drive: Preferred and legally allowed in Bangladesh.</li>
                            <li>Import duties: Expect 45% customs duty + 15% VAT + 2.5% regulatory duty on CIF value;
                                total can add 100%+ to the car's price.</li>
                            <li>Prohibited items: No salvage titles; ensure clean history.</li>
                        </ul>
                        <p>
                            Use our free consultation at Car Corporation to check eligibility and calculate costs based
                            on current NBR tariffs.
                        </p>

                        <h2 id="sourcing">2. Sourcing JDM Vehicles from Japan</h2>
                        <p>
                            Japan is the top source for reliable, affordable used cars in Bangladesh. Popular platforms
                            include:
                        </p>
                        <ul class="list-disc ml-6 mb-6">
                            <li>Japanese auctions via USS Tokyo or JU Yamaguchi (we bid on your behalf at Car
                                Corporation).</li>
                            <li>Online exporters like BE FORWARD or SBT Japan for direct purchases.</li>
                            <li>Dealerships in Japan for new/nearly-new models like the Toyota Vitz or Honda Fit.</li>
                            <li>Local networks: Join Bangladesh JDM Facebook groups for tips and deals.</li>
                        </ul>
                        <p>
                            Budget BDT 10-50 lakhs for the vehicle itself. Always request a detailed auction sheet and
                            third-party inspection—our service includes this to verify mileage and condition.
                        </p>

                        <h2 id="documentation">3. Prepare Essential Documentation</h2>
                        <p>
                            Accurate paperwork prevents delays at Chittagong Port. Essential documents for Bangladesh
                            imports:
                        </p>
                        <ul class="list-disc ml-6 mb-6">
                            <li>Export Certificate of Approval (from Japan exporter).</li>
                            <li>Commercial Invoice and Bill of Lading.</li>
                            <li>Certificate of Origin and DHL/Yellow Card for insurance.</li>
                            <li>Import Permit from Chief Controller of Imports & Exports (CCI&E).</li>
                            <li>VIN verification and emission certificate.</li>
                        </ul>
                        <p>
                            We at Car Corporation handle notarization and translation to Bengali/English as needed.
                        </p>

                        <h2 id="shipping">4. Arrange International Shipping</h2>
                        <p>
                            Shipping from Yokohama or Nagoya to Chittagong takes 20-30 days. Options include:
                        </p>
                        <ul class="list-disc ml-6 mb-6">
                            <li>RoRo (Roll-on/Roll-off): Cost-effective at ~BDT 1-2 lakhs, but exposed to elements.</li>
                            <li>Container (20ft): Safer for BDT 2-3 lakhs, ideal for multiple vehicles.</li>
                            <li>Our partnered lines like NYK or MOL ensure tracking and insurance up to USD 50,000.</li>
                        </ul>
                        <p>
                            Factor in port handling fees (~BDT 50,000) and demurrage. Track your shipment via our
                            dashboard.
                        </p>

                        <h2 id="customs">5. Clear Customs with NBR</h2>
                        <p>
                            Upon arrival, file with NBR at Chittagong Customs House:
                        </p>
                        <ul class="list-disc ml-6 mb-6">
                            <li>Submit Bill of Entry and pay duties (use ASYCUDA system).</li>
                            <li>Physical inspection for valuation and compliance.</li>
                            <li>Obtain Goods Declaration and release order.</li>
                            <li>Timeline: 3-7 days with a broker; we expedite for faster clearance.</li>
                        </ul>
                        <p>
                            Beware of undervaluation scams—our transparent process ensures compliance and saves on
                            penalties.
                        </p>

                        <h2 id="modifications">6. Make Required Modifications</h2>
                        <p>
                            JDM cars often need tweaks for Bangladeshi roads and standards:
                        </p>
                        <ul class="list-disc ml-6 mb-6">
                            <li>Convert odometer to km/h if needed (standard for JDM).</li>
                            <li>Install fog lights and adjust headlights for left-hand traffic.</li>
                            <li>Upgrade exhaust for BS-IV emissions (cost ~BDT 50,000-1 lakh).</li>
                            <li>Add reflectors and speed limiters per BRTA rules.</li>
                            <li>Our reconditioning center in Dhaka handles this, including rust-proofing for humid
                                climate.</li>
                        </ul>
                        <p>
                            Total mod cost: BDT 1-3 lakhs, depending on model.
                        </p>

                        <h2 id="registration">7. Register with BRTA</h2>
                        <p>
                            Finalize ownership at your local BRTA office:
                        </p>
                        <ul class="list-disc ml-6 mb-6">
                            <li>Submit customs papers, fitness certificate, and insurance (from bKash/rocket integrated
                                providers).</li>
                            <li>Pay registration fee (~BDT 20,000-50,000) and get blue book.</li>
                            <li>Vehicle fitness test for roadworthiness.</li>
                            <li>Affix number plates and pay annual token tax.</li>
                        </ul>
                        <p>
                            With Car Corporation, we manage the entire process, including fitness checks at our
                            showrooms. Drive legally within 1-2 weeks!
                        </p>

                        <p class="text-gray-700 leading-relaxed mt-8">
                            Importing to Bangladesh requires navigating duties and logistics, but with Car Corporation's
                            expertise—from auction bidding to BRTA registration—you can own your dream JDM car
                            affordably and legally. Contact us today for a personalized import plan. Total estimated
                            cost for a mid-range sedan: BDT 20-40 lakhs landed. Drive safe!
                        </p>
                    </div>
                    <div class="flex flex-wrap gap-2 mt-8 mb-6">
                        <span class="bg-primary/10 text-primary px-3 py-1 rounded-full text-sm">JDM Import</span>
                        <span class="bg-secondary/10 text-secondary px-3 py-1 rounded-full text-sm">Bangladesh
                            Guide</span>
                        <span class="bg-primary/10 text-primary px-3 py-1 rounded-full text-sm">Japan Auctions</span>
                        <span class="bg-secondary/10 text-secondary px-3 py-1 rounded-full text-sm">BRTA
                            Registration</span>
                        <span class="bg-primary/10 text-primary px-3 py-1 rounded-full text-sm">NBR Duties</span>
                    </div>

                    <div class="flex gap-4 text-sm text-gray-600 mb-8">
                        <button class="hover:text-blue-500 flex items-center gap-1">
                            <Icon icon="mdi:twitter" class="w-5 h-5 text-blue-500" />
                            Share on Twitter
                        </button>
                        <button class="hover:text-blue-500 flex items-center gap-1">
                            <Icon icon="mdi:facebook" class="w-5 h-5 text-blue-500" />
                            Share on Facebook
                        </button>
                    </div>
                </article>
                <aside class="lg:w-80 space-y-6 ">
                    <div class="bg-white p-6 rounded-lg shadow">
                        <div class="flex items-center gap-4 mb-4">
                            <img :src="author.avatar" :alt="author.name" class="w-16 h-16 rounded-full" />
                            <div>
                                <h3 class="font-semibold text-gray-500">{{ author.name }}</h3>
                                <p class="text-sm text-gray-600">Car Import Specialists</p>
                            </div>
                        </div>
                        <p class="text-gray-600">{{ author.bio }}</p>
                    </div>

                    <div class="bg-white p-6 rounded-lg shadow">
                        <h3 class="font-semibold mb-4 text-gray-500">Table of Contents</h3>
                        <nav class="space-y-2">
                            <a v-for="item in tocItems" :key="item.id" :href="`#${item.id}`"
                                class="block text-gray-600 hover:text-primary">{{ item.title }}</a>
                        </nav>
                    </div>
                    <div class="bg-white p-6 rounded-lg shadow">
                        <h3 class="font-semibold mb-4 text-gray-500">Related Articles</h3>
                        <ul class="space-y-3">
                            <li v-for="article in relatedArticles" :key="article.url">
                                <a :href="article.url" class="text-gray-600 hover:text-primary block">
                                    {{ article.title }}
                                </a>
                            </li>
                        </ul>
                    </div>
                    <div class="bg-white p-6 rounded-lg shadow">
                        <h3 class="font-semibold mb-4 text-gray-500">Subscribe for Import Tips</h3>
                        <p class="text-gray-600 mb-4">Get exclusive updates on Japan auctions and Bangladesh import
                            news!</p>
                        <form @submit.prevent="subscribeToNewsletter">
                            <input v-model="email" type="email" placeholder="Your email"
                                class="w-full p-2 border rounded mb-2" required />
                            <button type="submit"
                                class="w-full bg-primary text-white py-2 rounded hover:bg-primary/90 transition">
                                Subscribe
                            </button>
                        </form>
                    </div>
                </aside>
            </div>

            <section class="mt-12 pt-8 border-t">
                <h3 class="text-2xl font-semibold mb-6 text-gray-500">Comments ({{ comments.length }})</h3>

                <div class="bg-white p-6 rounded-lg shadow mb-8">
                    <h4 class="font-semibold mb-4 text-gray-500">Leave a Comment</h4>
                    <form @submit.prevent="submitComment">
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mb-4">
                            <div>
                                <label for="name" class="block text-sm font-medium text-gray-700 mb-1">Name</label>
                                <input v-model="newComment.author" type="text" id="name"
                                    class="w-full p-2 border rounded focus:ring-2 focus:ring-primary focus:border-transparent transition-all text-gray-500"
                                    placeholder="Enter your Name" required />
                            </div>
                            <div>
                                <label for="email" class="block text-sm font-medium text-gray-700 mb-1">Email</label>
                                <input v-model="newComment.email" type="email" id="email"
                                    class="w-full p-2 border rounded focus:ring-2 focus:ring-primary focus:border-transparent transition-all text-gray-500"
                                    placeholder="Enter you Email" required />
                            </div>
                        </div>
                        <div class="mb-4">
                            <label for="comment" class="block text-sm font-medium text-gray-700 mb-1">Comment</label>
                            <textarea v-model="newComment.content" id="comment" rows="4"
                                class="w-full p-2 border rounded focus:ring-2 focus:ring-primary focus:border-transparent transition-all text-gray-500"
                                placeholder="Give Your Comment here" required></textarea>
                        </div>
                        <button type="submit"
                            class="bg-primary text-white py-2 px-6 rounded hover:bg-primary/90 transition flex items-center gap-2">
                            <Icon icon="mdi:send-variant" class="w-5 h-5" />
                            Submit Comment
                        </button>
                    </form>
                </div>

                <div class="space-y-6">
                    <div v-for="comment in comments" :key="comment.id" class="bg-white p-6 rounded-lg shadow">
                        <div class="flex items-start gap-4">
                            <img :src="comment.avatar" :alt="comment.author" class="w-12 h-12 rounded-full" />
                            <div class="flex-1">
                                <div class="flex items-center gap-2 mb-2">
                                    <h4 class="font-semibold">{{ comment.author }}</h4>
                                    <span class="text-sm text-gray-500">{{ comment.date.toLocaleDateString() }}</span>
                                </div>
                                <p class="text-gray-700">{{ comment.content }}</p>
                            </div>
                        </div>
                    </div>
                </div>
            </section>
        </div>
    </div>
</template>

<style scoped></style>