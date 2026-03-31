<template>
  <header class="sticky top-0 z-50 bg-white font-poppins shadow-[0_5px_10px_rgba(19,99,223,.25)]">
    <nav class="mx-auto flex max-w-7xl items-center justify-between p-4 lg:px-8" aria-label="Global">
      <!-- Logo -->
      <div class="flex lg:flex-1">
        <a href="#" class="-m-1.5 p-1.5">
          <img :src="logo" :alt="logoAlt" class="h-10 w-10 lg:h-12 lg:w-12" />
        </a>
      </div>  

      <!-- Mobile menu button -->
      <div class="flex lg:hidden">
        <button type="button" @click="mobileMenuOpen = true"
          class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5 text-gray-700">
          <span class="sr-only">Open main menu</span>
          <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"
            aria-hidden="true">
            <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" />
          </svg>
        </button>
      </div>

      <!-- Desktop navigation -->
      <div class="hidden lg:flex lg:gap-x-8">
        <a v-for="link in navLinks" :key="link.title" :href="link.href"
          class="text-sm font-semibold leading-6 text-gray-900 hover:text-[#0245A3] transition-colors">
          {{ link.title }}
        </a>
      </div>

      <!-- Desktop utility buttons -->
      <div class="hidden lg:flex lg:flex-1 lg:justify-end lg:items-center lg:gap-x-6">
        <a href="#" class="inline-flex items-center justify-center rounded-lg bg-[#0245A3] px-6 py-2.5 text-sm font-semibold text-white shadow-sm hover:bg-[#023B8A] transition-colors">
          Log in
        </a>

        <!-- Desktop Language Dropdown -->
        <div class="relative">
          <button type="button" @click="langMenuOpen = !langMenuOpen"
            class="flex items-center gap-x-1 rounded-md bg-white px-3 py-2 text-sm font-semibold text-[#0245A3] shadow-sm ring-1 ring-inset ring-[#0245A3] hover:bg-gray-50 transition-colors"
            id="language-menu-button" aria-expanded="false" aria-haspopup="true">
            Language
            <svg class="h-5 w-5 text-[#0245A3]" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
              <path fill-rule="evenodd"
                d="M5.23 7.21a.75.75 0 011.06.02L10 11.168l3.71-3.938a.75.75 0 111.08 1.04l-4.25 4.5a.75.75 0 01-1.08 0l-4.25-4.5a.75.75 0 01.02-1.06z"
                clip-rule="evenodd" />
            </svg>
          </button>

          <!-- Dropdown panel -->
          <div v-show="langMenuOpen" @click.away="langMenuOpen = false"
            class="absolute right-0 z-10 mt-2 w-48 origin-top-right rounded-md bg-white shadow-lg ring-1 ring-black ring-opacity-5 focus:outline-none"
            role="menu" aria-orientation="vertical" aria-labelledby="language-menu-button" tabindex="-1">
            <div class="py-1" role="none">
              <a v-for="lang in language" :key="lang.title" :href="lang.href"
                class="block px-4 py-2 text-sm text-[#0245A3] hover:bg-gray-100" role="menuitem" tabindex="-1">
                {{ lang.title }}
              </a>
            </div>
          </div>
        </div>
      </div>
    </nav>

    <!-- Mobile menu overlay -->
    <div v-if="mobileMenuOpen" class="lg:hidden" role="dialog" aria-modal="true">
      <!-- Background backdrop -->
      <div class="fixed inset-0 z-50 bg-black/30" @click="mobileMenuOpen = false"></div>

      <!-- Mobile menu drawer -->
      <div
        class="fixed inset-y-0 right-0 z-50 w-full overflow-y-auto bg-white px-6 py-6 sm:max-w-sm sm:ring-1 sm:ring-gray-900/10">
        <div class="flex items-center justify-between">
          <a href="#" class="-m-1.5 p-1.5">
            <img :src="logo" :alt="logoAlt" class="h-10 w-10" />
          </a>
          <button type="button" @click="mobileMenuOpen = false" class="-m-2.5 rounded-md p-2.5 text-gray-700">
            <span class="sr-only">Close menu</span>
            <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"
              aria-hidden="true">
              <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
        </div>

        <div class="mt-6 flow-root">
          <div class="-my-6 divide-y divide-gray-500/10">
            <div class="space-y-2 py-6">
              <a v-for="link in navLinks" :key="link.title" :href="link.href"
                class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50">
                {{ link.title }}
              </a>
            </div>

            <div class="py-6">
              <div class="flex flex-col gap-4">
                <a href="#"
                  class="inline-flex items-center justify-center rounded-md bg-[#0245A3] px-4 py-2 text-sm font-semibold text-white shadow-sm hover:bg-blue-700 transition-colors">
                  Log in
                </a>

                <!-- Mobile Language selector -->
                <div class="relative">
                  <button @click="mobileLangOpen = !mobileLangOpen"
                    class="flex w-full items-center justify-between rounded-md bg-white px-3 py-2 text-sm font-semibold text-[#0245A3] shadow-sm ring-1 ring-inset ring-[#0245A3]">
                    Language
                    <svg class="h-5 w-5 text-[#0245A3]" :class="{ 'rotate-180': mobileLangOpen }" viewBox="0 0 20 20"
                      fill="currentColor" aria-hidden="true">
                      <path fill-rule="evenodd"
                        d="M5.23 7.21a.75.75 0 011.06.02L10 11.168l3.71-3.938a.75.75 0 111.08 1.04l-4.25 4.5a.75.75 0 01-1.08 0l-4.25-4.5a.75.75 0 01.02-1.06z"
                        clip-rule="evenodd" />
                    </svg>
                  </button>
                  <div v-show="mobileLangOpen" class="mt-2 space-y-1 px-2 transition-all">
                    <a v-for="lang in language" :key="lang.title" :href="lang.href"
                      class="block rounded-md px-3 py-2 text-sm font-medium text-[#0245A3] hover:bg-gray-50">
                      {{ lang.title }}
                    </a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref } from 'vue'
import imgSrc from '@/assets/images/ob-logo.svg'

const mobileMenuOpen = ref(false)
const langMenuOpen = ref(false)
const mobileLangOpen = ref(false)

const logo = ref(imgSrc)
const logoAlt = 'Objob logo'

const navLinks = [
  { title: 'Find Jobs', href: '#' },
  { title: 'Companies', href: '#' },
  { title: 'Services', href: '#' },
  { title: 'For Employers', href: '#' },
]

const language = [
  { title: 'English', href: '#' },
  { title: 'Arabic', href: '#' },
]
</script>

<style scoped>
/* Ensure the transition is smooth for the rotate icon */
svg {
  transition: transform 0.2s;
}
</style>
