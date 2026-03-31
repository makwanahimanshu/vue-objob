<template>
  <section class="w-full py-12 font-poppins">
    <div class="max-w-[1240px] mx-auto px-6">
      <div class="">
        <div class="leading-3">
          <h1
            class="text-[#0245A3] text-[40px] font-[700] text-left uppercase pb-8 tracking-[0.50px]"
          >
            {{ ourNumbers }}
          </h1>
        
        </div>
        <div class="grid grid-cols-3 gap-3 pt-4 flex items-center capitalize">
            <div class="items-center gap-2">
                <p class="text-[50px] font-[900] text-left text-black">14,000</p>
                <p class="text-[15px] font-[500] text-left text-[#0245A3]">New Registered candidates in 30 days</p>
            </div>
            <div class="items-center gap-2">
                <p class="text-[50px] font-[900] text-left text-black">100,000</p>
                <p class="text-[15px] font-[500] text-left text-[#0245A3]">Total registered candidates</p>
            </div>
            <div class="items-center gap-2">
                <p class="text-[50px] font-[900] text-left text-black">2100</p>
                <p class="text-[15px] font-[500] text-left text-[#0245A3]">New opportunities posted in 30 days</p>
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
