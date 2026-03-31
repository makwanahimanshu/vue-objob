<template>
  <section class="w-full py-8 font-poppins">
    <div class="max-w-[1240px] mx-auto px-6">
      <h1 class="text-[#0245A3] text-[35px] font-[900] text-left uppercase pb-8 tracking-normal">
        {{ findJobsByIndustries }}
      </h1>
      <div class="grid grid-cols-4 gap-6 text-black leading-6">
        <div
          class="p-6 border border-[#D9D9D9] rounded-[15px] shadow-[0_5px_10px_rgba(19,99,223,.25)] bg-[#EFEFEF] hover:bg-white hover:border-[#0245A3] hover:text-[#0245A3]"
         v-for="(job, index) in jobs" :key="index">
          <div class="text-[22px] font-[700] uppercase text-left capitalize">
            {{ job.title }}
          </div>
          <p class="text-[16px] font-[500] text-left capitalize pt-3">{{ job.jobs }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

let findJobsByIndustries = ref('Find jobs by industries');

let jobs = ref([
  { title: 'Information & technology', jobs: '360 jobs Openings' },
  { title: 'Automative industries', jobs: '126 jobs Openings' },
  { title: 'Retail shops & malls', jobs: '107 jobs Openings' },
  { title: 'Logistics & transportation', jobs: '710 jobs Openings' },
  { title: 'Fashion industries', jobs: '54 jobs Openings' },
  { title: 'Hospitality & tourism', jobs: '1410 jobs Openings' },
  { title: 'Medical & healthcare', jobs: '354 jobs Openings' },
  { title: 'Engineering & construction', jobs: '657 jobs Openings' },
]);
</script>
