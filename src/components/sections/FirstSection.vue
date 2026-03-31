<template>
  <section class="w-full font-poppins">
    <div class="relative pt-14 px-6 lg:px-8 max-w-[1280px] mx-auto text-center">
      <div class="flex flex-col-reverse lg:grid lg:grid-cols-[1fr_1fr_auto] gap-6 lg:gap-4 lg:text-left items-center lg:items-stretch">
        <div class="w-full text-center lg:text-left">
          <h1 class="text-black text-[18px] lg:text-[20px] font-[500] uppercase pb-4 tracking-wide">
            {{ mostTrusted }}
          </h1>
          <p
            class="leading-[110%] lg:leading-[100%] text-[32px] lg:text-[48px] font-[800] uppercase w-full lg:w-[510px] mx-auto lg:mx-0 text-[#0245A3] pb-4"
          >
            {{ newVentures }}
          </p>

          <p class="text-black text-[16px] lg:text-[20px] font-[400] capitalize pb-12 tracking-normal">
            {{ findingJob }} <br class="lg:block hidden" />
            {{ jobDescription }}
          </p>

          <div
            class="grid grid-cols-1 lg:grid-cols-[320px_250px_180px] gap-4 lg:gap-2 border border-[#0245A3] py-6 px-4 rounded-[15px] shadow-[0_5px_10px_rgba(19,99,223,.25)] z-10 relative lg:absolute bg-white align-center text-left mx-auto lg:mx-0"
          >
            <div class="px-2 py-2 lg:py-4 flex items-center gap-2 justify-center lg:justify-start">
              <img :src="firstSearchLogo" :alt="firstSearchLogoAlt" class="h-[20px] w-[20px]" />
              Search by Title, Skill, Category
            </div>
            <div
              class="px-2 py-2 lg:py-4 border-t lg:border-t-0 lg:border-l-3 lg:border-[#0245A3] flex items-center gap-4 justify-center lg:justify-start"
            >
              <img :src="secondCountryLogo" :alt="secondCountryLogoAlt" class="h-[20px] w-[20px]" />
              Select Country
            </div>
            <div class="px-2 flex items-center justify-center">
              <button
                class="bg-[#0245A3] lg:bg-white text-white lg:text-[#0245A3] w-full lg:w-auto px-12 py-3 lg:py-4 rounded-[14px] font-[600] uppercase border border-[#0245A3] cursor-pointer"
              >
                Search
              </button>
            </div>
          </div>
        </div>
        <div class="flex justify-center lg:justify-end pb-8 lg:pb-0">
          <img :src="heroImage" :alt="heroImageAlt" class="max-w-[100%] lg:max-w-[640px] relative lg:top-[-50px]" />
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
