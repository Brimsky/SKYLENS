<template>
    <div class="antialiased mx-auto bg-gray-100">
        <!-- Hero Section -->
        <
        <div class="relative h-screen overflow-hidden">
            <transition name="fade" mode="out-in">
                <video
                    :key="currentBg"
                    :src="videos[currentBg]"
                    class="absolute inset-0 object-cover w-full h-full"
                    autoplay
                    muted
                    loop
                ></video>
            </transition>

            <div class="relative z-10 flex items-center justify-center h-full">
                <h1
                    class="text-center text-4xl sm:text-5xl font-bold leading-tight max-w-3xl mx-auto text-white"
                >
                    <transition name="font-change" mode="out-in">
                        <span :key="currentFont" :class="fonts[currentFont]">
                            CHANGE
                        </span>
                    </transition>
                    THE WAY OF VIEW
                </h1>
            </div>
        </div>

        <!-- About Section -->
        <div class="py-16 px-4 sm:px-6 lg:px-8">
            <div class="max-w-3xl mx-auto">
                <h2
                    class="text-black font-bold text-2xl sm:text-3xl mb-4 text-center"
                >
                    YOUR ULTIMATE DRONE FOOTAGE PROVIDER
                </h2>
                <p class="text-gray-700 text-lg text-center mb-8">
                    At Skylens, we specialize in capturing stunning aerial
                    footage and high-quality photos tailored to your specific
                    needs. Our nationwide network of experienced drone operators
                    ensures that every project is handled with precision and
                    delivered on time.
                </p>
                <latviaimg class="w-full h-auto max-w-md mx-auto"></latviaimg>
            </div>
        </div>

        <!-- Features Section -->
        <div class="py-16 px-4 sm:px-6 lg:px-8">
            <div class="max-w-3xl mx-auto space-y-16">
                <div class="flex flex-col md:flex-row items-center">
                    <img
                        :src="statue"
                        alt="Statue Image"
                        class="w-full md:w-1/2 h-auto mb-4 md:mb-0 md:mr-8"
                    />
                    <div>
                        <h2 class="text-3xl font-bold mb-4">
                            THE BEST VIDEO QUALITY AVAILABLE
                        </h2>
                    </div>
                </div>
                <div class="flex flex-col md:flex-row-reverse items-center">
                    <img
                        :src="house"
                        alt="House Image"
                        class="w-full md:w-1/2 h-auto mb-4 md:mb-0 md:ml-8"
                    />
                    <div>
                        <h2 class="text-3xl font-bold mb-4">
                            BEST PROPERTY ANGLES
                        </h2>
                    </div>
                </div>
            </div>
        </div>

        <!-- Pricing Section -->
        <div class="py-16 px-4 sm:px-6 lg:px-8">
            <div class="max-w-5xl mx-auto">
                <h2
                    class="text-3xl sm:text-4xl font-extrabold text-center mb-12"
                >
                    PRICING
                </h2>
                <div class="grid gap-8 md:grid-cols-3">
                    <div
                        v-for="plan in plans"
                        :key="plan.title"
                        class="bg-white border border-gray-200 p-6"
                    >
                        <h3 class="text-xl font-semibold text-gray-900 mb-4">
                            {{ plan.title }}
                        </h3>
                        <p class="text-3xl font-extrabold text-gray-900 mb-6">
                            ${{ plan.price
                            }}<span class="text-xl font-medium text-gray-500"
                                >/month</span
                            >
                        </p>
                        <ul class="space-y-2 mb-6">
                            <li
                                v-for="(feature, index) in plan.features"
                                :key="index"
                                class="flex items-start"
                            >
                                <span class="text-sm text-gray-700">{{
                                    feature
                                }}</span>
                            </li>
                        </ul>
                        <button
                            class="w-full bg-black text-white py-2 px-4 text-sm font-semibold hover:bg-gray-800 transition-colors duration-200"
                        >
                            Select Plan
                        </button>
                    </div>
                </div>
            </div>
        </div>

        <!-- Footer -->
        <footer class="bg-white text-white py-6">
            <div
                class="container mx-auto flex justify-between items-center px-4"
            >
                <div class="flex items-center">
                    <img :src="logo" alt="Skylens" class="h-8 w-auto mr-2" />
                </div>
                <div class="flex space-x-4">
                    <a href="#" class="text-gray-400 hover:text-white">
                        <span class="sr-only">Twitter</span>
                        <img
                            :src="twiterX"
                            class="h-6 w-6"
                            fill="currentColor"
                            viewBox="0 0 24 24"
                            aria-hidden="true"
                        />
                    </a>
                    <a href="#" class="text-gray-400 hover:text-white">
                        <span class="sr-only">Instagram</span>
                        <img
                            :src="instagram"
                            class="h-6 w-6"
                            fill="currentColor"
                            viewBox="0 0 24 24"
                            aria-hidden="true"
                        />
                    </a>
                    <a href="#" class="text-gray-400 hover:text-white">
                        <span class="sr-only">YouTube</span>
                        <img
                            :src="youtube"
                            class="h-6 w-6"
                            fill="currentColor"
                            viewBox="0 0 24 24"
                            aria-hidden="true"
                        />
                    </a>
                </div>
            </div>
        </footer>
    </div>
</template>

<script setup>
import latviaimg from "@/utils/svg/latvia.vue";
import statue from "@/utils/img/statue.png";
import house from "@/utils/img/house.png";
import logo from "../utils/img/skylens.png";
import twiterX from "../utils/img/twitterx-100.png";
import instagram from "../utils/img/instagram-100.png";
import youtube from "../utils/img/youtube-100.png";
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

import { ref, onMounted, onUnmounted } from "vue";

const videos = [
    "/path/to/video1.mp4",
    "/path/to/video2.mp4",
    "/path/to/video3.mp4",
];

const fonts = ["font-serif", "font-sans", "font-mono"];

const currentBg = ref(0);
const currentFont = ref(0);
let intervalId;

const changeBackground = () => {
    currentBg.value = (currentBg.value + 1) % videos.length;
    currentFont.value = (currentFont.value + 1) % fonts.length;
};

onMounted(() => {
    intervalId = setInterval(changeBackground, 5000); // Change every 5 seconds

    // Stop the animation after 30 seconds
    setTimeout(() => {
        clearInterval(intervalId);
    }, 30000);
});

onUnmounted(() => {
    clearInterval(intervalId);
});
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
    transition: opacity 1s ease;
}

.fade-enter-from,
.fade-leave-to {
    opacity: 0;
}

.font-change-enter-active,
.font-change-leave-active {
    transition: all 0.5s ease;
}

.font-change-enter-from,
.font-change-leave-to {
    opacity: 0;
    transform: scale(0.9);
}
</style>
