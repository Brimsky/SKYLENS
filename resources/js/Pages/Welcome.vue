<script setup>
import { Link } from '@inertiajs/vue3';
import { computed } from 'vue';
//conponents
//------icons
import logo from '../utils/img/skylens.png';
import userlight from '../utils/img/user/user-light.png';

//------page components
import pagecontent from '../Components/Homepage.vue';

//------page utils
import Dropdown from '@/Components/Dropdown.vue';
import DropdownLink from '@/Components/DropdownLink.vue';




// import { useDark, useToggle} from '@vueuse/core';
  
// import lightIcon from '../icons/Logo/icon.png';
// import darkIcon from '../icons/Logo/darkicon.png';
  
// import lightmode from '../icons/Mode/sun.png'
// import darkmode from '../icons/Mode/moon.png'


// const isDark = useDark();
// const toggleDark = useToggle(isDark);
// // console.log(isDark.value);

// const mode = computed(() => isDark.value ? darkmode : lightmode);
// const iconSrc = computed(() => isDark.value ? darkIcon : lightIcon);
import { defineProps } from 'vue';
defineProps({
    canLogin: {
        type: Boolean,
        required: true,
    },
    canRegister: {
        type: Boolean,
        required: true,
    },
    laravelVersion: {
        type: String,
        required: true,
    },
    phpVersion: {
        type: String,
        required: true,
    },
});

import { ref } from 'vue';



const open = ref(false)
</script>

<template class="antialiased md:w-auto">
<!-- Navbar -->
<div class="text-white  dark:bg-neutral-800 flex h-[60px] m-0 px-[35px] py-0 rounded-b-lg">
    <div class="flex items-center justify-center mx-auto w-11/12">
      <div class="container flex items-center ">
        <a href="/">
          <img class="h-20 w-20" :src="logo" alt="Icon" />
        </a>
        <a  href="/" class="dark:text-white text-black text-3xl tracking-wider font-bold">SKYLENS</a>
        </div>

        <div>
          <div class="md:hidden">
            <button @click="open = !open" class="p-4 focus:outline-none">
              <svg v-show="!open" xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h7"/>
              </svg>
              <svg v-show="open" xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
              </svg>
            </button>
            
          <div v-show="open" class="absolute top-0 left-0 w-full bg-neutral-900 text-white z-50">
            <div class="flex items-center justify-between px-4 py-3 border-b border-gray-700">
              <a href="/" class="text-xl font-semibold">SKYLENS</a>
              <button @click="open = false" class="text-gray-400 focus:outline-none">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
                </svg>
              </button>
      </div>

      <div class="px-2 py-2 space-y-1">
        <a v-if="canLogin">
          <a v-if="$page.props.auth.user">
            <a href="/dashboard" class="block px-3 py-2 rounded-md text-base font-medium bg-neutral-700 text-white">Dashboard</a>
          </a>
          <a v-else class="px-2 py-1 rounded-md">
            <a :href="route('login')" class="block px-3 py-2 rounded-md text-base font-medium bg-neutral-700 text-white">Log in</a>
            <a v-if="canRegister" class=" px-2 py-1 rounded-md">
              <a :href="route('register')" class="block px-3 py-2 rounded-md text-base font-medium bg-neutral-700 text-white">Sing up</a>
            </a>
          </a>
        </a>
      </div>
    </div>
  </div>

  </div>
      <!-- <div v-if="canLogin" class="items-center space-x-6  hidden md:flex">
        <template v-if="$page.props.auth.user">
          <Link :href="route('dashboard')"
                class="navbar-btn">
            Dashboard
          </Link>
          <button @click="toggleDark()"
                  class="py-2 px-4 bg-stone-900 hover:bg-stone-700 dark:hover:bg-stone-400 dark:bg-white  text-white font-bold rounded-xl shadow-md transition duration-150">
            <img class="h-7" :src="mode" alt="Dark Mode Icon" />
          </button>
        </template>
        <template v-else>
          <Link :href="route('login')"
                class="navbar-btn">
            Log in
          </Link>
          <Link v-if="canRegister" :href="route('register')"
                class="navbar-btn">
            Register
          </Link>
          button @click="toggleDark()"
                  class="py-2 px-4 bg-stone-900 hover:bg-stone-700 dark:hover:bg-stone-400 dark:bg-white  text-white font-bold rounded-xl shadow-md transition duration-150">
            <img class="h-7" :src="mode" alt="Dark Mode Icon" />
          </button>
        </template>
      </div> -->
      <div class="items-center space-x-6 space-y-2  hidden md:flex">
        <div class="md:flex space-x-8 items-center w-full whitespace-nowrap ">
          <h2>PRICING</h2>
          <h2>ABAOUT US</h2>
        </div>
        
      </div>
      <div class="ms-3 relative">
          <Dropdown align="right" width="48">
            <template #trigger>
              <span class="inline-flex rounded-md">
                <button
                type="button"
                class="inline-flex items-center px-3 py-2 border border-transparent text-sm leading-4 font-medium rounded-md text-gray-500  hover:text-gray-700 focus:outline-none transition ease-in-out duration-150"
                >
                <img class="scale-50" :src="userlight" alt="Icon" />
            </button>
          </span>
        </template>
        <template #content>
          <DropdownLink :href="route('login')"> LOG IN </DropdownLink>
          <DropdownLink :href="route('register')"> SIGN UP </DropdownLink>
        </template>
        </Dropdown>
      </div>
    </div>
</div>

<pagecontent/>

</template>
