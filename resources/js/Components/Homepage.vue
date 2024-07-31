<template>
    <div class="antialiased mx-auto">
        <!-- Hero Section -->
        <div
            class="bg-gradient-to-r from-indigo-500 via-purple-500 to-pink-500 py-20 px-4 sm:px-6 lg:px-8"
        >
            <h1
                class="text-white text-center text-3xl sm:text-5xl font-bold leading-tight max-w-3xl mx-auto"
            >
                CHANGE THE WAY YOU VIEW THE WORLD
            </h1>
        </div>

        <!-- About Section -->
        <div class="bg-white py-16 px-4 sm:px-6 lg:px-8">
            <div class="max-w-7xl mx-auto">
                <div class="lg:flex items-center justify-between">
                    <div class="lg:w-1/2 mb-8 lg:mb-0">
                        <h2
                            class="text-black font-bold text-2xl sm:text-3xl mb-4"
                        >
                            YOUR ULTIMATE DRONE FOOTAGE PROVIDER
                        </h2>
                        <p class="text-gray-700 text-lg">
                            At Skylens, we specialize in capturing stunning
                            aerial footage and high-quality photos tailored to
                            your specific needs. Our nationwide network of
                            experienced drone operators ensures that every
                            project is handled with precision and delivered on
                            time.
                        </p>
                    </div>
                    <div class="lg:w-1/2 lg:pl-12">
                        <latviaimg class="w-full h-auto"></latviaimg>
                    </div>
                </div>
            </div>
        </div>

        <!-- Features Section -->
        <div class="bg-gray-100 py-16 px-4 sm:px-6 lg:px-8">
            <div class="max-w-7xl mx-auto">
                <div class="lg:flex items-center justify-between mb-16">
                    <div class="lg:w-1/2 mb-8 lg:mb-0">
                        <img
                            :src="statue"
                            alt="Statue Image"
                            class="w-full h-auto rounded-lg shadow-lg"
                        />
                    </div>
                    <div class="lg:w-1/2 lg:pl-12">
                        <h2 class="text-3xl font-bold mb-4">
                            The best video quality available
                        </h2>
                        <p class="text-gray-700">
                            Experience unparalleled clarity and detail in every
                            shot.
                        </p>
                    </div>
                </div>
                <div
                    class="lg:flex items-center justify-between flex-row-reverse"
                >
                    <div class="lg:w-1/2 mb-8 lg:mb-0">
                        <img
                            :src="house"
                            alt="House Image"
                            class="w-full h-auto rounded-lg shadow-lg"
                        />
                    </div>
                    <div class="lg:w-1/2 lg:pr-12">
                        <h2 class="text-3xl font-bold mb-4">
                            Best property angles
                        </h2>
                        <p class="text-gray-700">
                            Showcase properties from their most flattering
                            perspectives.
                        </p>
                    </div>
                </div>
            </div>
        </div>

        <!-- Pricing Section -->
        <div class="bg-white py-16 px-4 sm:px-6 lg:px-8">
            <div class="max-w-7xl mx-auto">
                <h2
                    class="text-3xl sm:text-4xl font-extrabold text-center mb-12"
                >
                    PRICING
                </h2>
                <div class="grid gap-8 md:grid-cols-2 lg:grid-cols-3">
                    <div
                        v-for="plan in plans"
                        :key="plan.title"
                        class="bg-white rounded-lg shadow-lg overflow-hidden border border-gray-200 transition-transform duration-300 hover:scale-105"
                    >
                        <div class="px-6 py-8">
                            <h3
                                class="text-2xl font-semibold text-gray-900 mb-4"
                            >
                                {{ plan.title }}
                            </h3>
                            <p
                                class="text-4xl font-extrabold text-gray-900 mb-6"
                            >
                                ${{ plan.price
                                }}<span
                                    class="text-xl font-medium text-gray-500"
                                    >/month</span
                                >
                            </p>
                            <ul class="space-y-4">
                                <li
                                    v-for="(feature, index) in plan.features"
                                    :key="index"
                                    class="flex items-start"
                                >
                                    <svg
                                        class="h-6 w-6 text-green-500 mr-3"
                                        fill="none"
                                        viewBox="0 0 24 24"
                                        stroke="currentColor"
                                    >
                                        <path
                                            stroke-linecap="round"
                                            stroke-linejoin="round"
                                            stroke-width="2"
                                            d="M5 13l4 4L19 7"
                                        />
                                    </svg>
                                    <span class="text-gray-700">{{
                                        feature
                                    }}</span>
                                </li>
                            </ul>
                        </div>
                        <div class="px-6 py-4 bg-gray-50">
                            <button
                                class="w-full bg-indigo-600 text-white rounded-md py-3 px-4 text-lg font-semibold hover:bg-indigo-700 transition-colors duration-200"
                            >
                                Select Plan
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import latviaimg from "@/utils/svg/latvia.vue";
import statue from "@/utils/img/statue.png";
import house from "@/utils/img/house.png";
import { ref } from "vue";

const plans = ref([
    {
        title: "Basic Plan",
        price: 50,
        features: [
            "5 drone flights per month",
            "HD video quality",
            "Basic editing included",
            "24/7 customer support",
            "Cloud storage (50GB)",
            "Monthly report",
            "1 revision per project",
        ],
    },
    {
        title: "Pro Plan",
        price: 100,
        features: [
            "15 drone flights per month",
            "4K video quality",
            "Advanced editing included",
            "Priority customer support",
            "Cloud storage (200GB)",
            "Weekly reports",
            "3 revisions per project",
        ],
    },
    {
        title: "Enterprise Plan",
        price: 250,
        features: [
            "Unlimited drone flights",
            "8K video quality",
            "Premium editing & effects",
            "Dedicated account manager",
            "Unlimited cloud storage",
            "Real-time reporting",
            "Unlimited revisions",
        ],
    },
]);
</script>
