<template>
  <section class="w-full font-poppins">
    <div class="relative pt-14 px-6 lg:px-8 max-w-[1280px] mx-auto text-center">
      <div class="grid grid-cols-[1fr_1fr_auto] gap-4">
        <div class="">
          <h1 class="text-black text-[20px] font-[500] text-left uppercase pb-4 tracking-wide">
            {{ mostTrusted }}
          </h1>
          <p
            class="leading-[100%] text-[48px] font-[800] text-left uppercase w-[510px] text-[#0245A3] pb-4"
          >
            {{ newVentures }}
          </p>

          <p class="text-black text-[20px] font-[400] text-left capitalize pb-12 tracking-normal">
            {{ findingJob }} <br class="md:block hidden" />
            {{ jobDescription }}
          </p>

          <div
            class="grid grid-cols-[320px_250px_180px] gap-2 border border-[#0245A3] py-6 px-4 rounded-[15px] shadow-[0_5px_10px_rgba(19,99,223,.25)] z-10 absolute bg-white align-center"
          >
            <div class="px-2 py-4 flex items-center gap-2 justify-center">
              <img :src="firstSearchLogo" :alt="firstSearchLogoAlt" class="h-[20px] w-[20px]" />
              Search by Title, Skill, Category
            </div>
            <div
              class="px-2 py-4 border-l-3 border-l-[#0245A3] flex items-center gap-4 justify-center"
            >
              <img :src="secondCountryLogo" :alt="secondCountryLogoAlt" class="h-[20px] w-[20px]" />
              Select Country
            </div>
            <div class="px-2 flex items-center justify-center">
              <button
                class="bg-white text-[#0245A3] px-12 py-4 rounded-[14px] font-[600] uppercase border border-[#0245A3] cursor-pointer"
              >
                Search
              </button>
            </div>
          </div>
        </div>
        <div class="flex justify-end">
          <img :src="heroImage" :alt="heroImageAlt" class="max-w-[640px] relative top-[-50px]" />
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import imgSrc from '@/assets/images/first_section_logo.svg'
import searchLogo from '@/assets/images/search.svg'
import countryLogo from '@/assets/images/world.svg'

let heroImage = ref(imgSrc)
let heroImageAlt = 'Hero Section Image'

let firstSearchLogo = ref(searchLogo)
let firstSearchLogoAlt = 'Search Logo'

let secondCountryLogo = ref(countryLogo)
let secondCountryLogoAlt = 'Country Logo'

let mostTrusted = ref('Most Trusted platform for jobs')
let newVentures = ref('New Ventures are waiting for you!')
let findingJob = ref('finding a job is now easier')
let jobDescription = ref('just find a job you like and apply the one you need')
</script>
