<template>
    <section class="w-full py-12 font-poppins">
        <div class="max-w-[1240px] mx-auto px-6">
            <div class="flex flex-col text-center md:text-left">
                <div class="leading-tight">
                    <h1 class="text-[#0245A3] text-[28px] md:text-[40px] font-[700] uppercase pb-2 md:pb-8 tracking-[0.50px]">
                        {{ findJobs }}
                    </h1>

                </div>
                <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-5 gap-6 lg:gap-3 pt-8 md:pt-4">
                    <div class="flex flex-col items-center md:items-stretch gap-2 border-1 border-[#0245A3] rounded-[12px] p-4 hover:shadow-lg transition-all"
                        v-for="(value, index) in myObject" :key="index">
                        <p class="text-black text-[16px] font-[700] hover:text-[#0245A3] cursor-pointer capitalize text-center md:text-left">{{
                            value.countryName }}</p>
                        <div class="flex justify-center items-center py-6 md:py-10">
                            <img :src="value.countryImg" alt="" class="h-[100px] w-auto max-w-full object-contain" />
                        </div>
                        <div class="flex justify-between items-center gap-2 text-[16px] font-[500]">
                            <p>{{ value.noOfJobs }} jobs</p>
                            <div
                                class="border border-[#0245A3] rounded-[50%] bg-[#0245A3] hover:text-white cursor-pointer p-2">
                                <img :src="rightArrowBtnImg" alt="" class="h-[20px] w-[20px]" />
                            </div>
                        </div>
                    </div>
                </div>
            </div>

        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue'

let findJobs = ref('Find Jobs by countries')
import rightArrowBtn from '@/assets/images/right_arrow.svg'
import countryImg1 from '@/assets/images/country1.jpg'
import countryImg2 from '@/assets/images/country2.jpg'
import countryImg3 from '@/assets/images/country3.jpg'
import countryImg4 from '@/assets/images/country4.jpg'
import countryImg5 from '@/assets/images/country5.jpg'

let rightArrowBtnImg = ref(rightArrowBtn)
let conImg1 = ref(countryImg1)
let conImg2 = ref(countryImg2)
let conImg3 = ref(countryImg3)
let conImg4 = ref(countryImg4)
let conImg5 = ref(countryImg5)

let myObject = ref([
    {
        countryName: 'Egypt',
        countryImg: conImg1,
        noOfJobs: 743
    },
    {
        countryName: 'United arab emirates',
        countryImg: conImg2,
        noOfJobs: 743
    },
    {
        countryName: 'qatar',
        countryImg: conImg3,
        noOfJobs: 743
    },
    {
        countryName: 'kuwait',
        countryImg: conImg4,
        noOfJobs: 743
    },
    {
        countryName: 'saudi arabia',
        countryImg: conImg5,
        noOfJobs: 743
    }
])
</script>
