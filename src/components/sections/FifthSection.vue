<template>
  <section class="w-full py-12 font-poppins">
    <div class="max-w-[1240px] mx-auto px-6">
      <div class="flex flex-col text-center md:text-left">
        <div class="leading-tight">
          <h1
            class="text-[#0245A3] text-[28px] md:text-[40px] font-[700] uppercase pb-2 md:pb-8 tracking-[0.50px]"
          >
            {{ ourNumbers }}
          </h1>
        
        </div>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8 md:gap-3 pt-4 md:pt-8 items-center capitalize text-center md:text-left">
            <div class="flex flex-col items-center md:items-start gap-1">
                <p class="text-[40px] md:text-[50px] font-[900] text-black leading-none">14,000</p>
                <p class="text-[14px] md:text-[15px] font-[500] text-[#0245A3]">New Registered candidates in 30 days</p>
            </div>
            <div class="flex flex-col items-center md:items-start gap-1">
                <p class="text-[40px] md:text-[50px] font-[900] text-black leading-none">100,000</p>
                <p class="text-[14px] md:text-[15px] font-[500] text-[#0245A3]">Total registered candidates</p>
            </div>
            <div class="flex flex-col items-center md:items-start gap-1">
                <p class="text-[40px] md:text-[50px] font-[900] text-black leading-none">2100</p>
                <p class="text-[14px] md:text-[15px] font-[500] text-[#0245A3]">New opportunities posted in 30 days</p>
            </div>
        </div>
     </div>

    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

let ourNumbers = ref('Our numbers speak for themselves.')



</script>
