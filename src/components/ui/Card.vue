<template>
    <div class="border-1 border-[#C6C6C6] rounded-[12px] p-4 hover:border-[#0245A3] relative h-auto min-h-[320px] pb-[80px] bg-white transition-all">
        <div class="flex flex-col sm:flex-row gap-4 sm:gap-3 pb-4">
            <div class="border-3 border-[#0245A3] rounded-full p-1 w-[80px] h-[80px] sm:w-[110px] sm:h-[110px] shrink-0 mx-auto sm:mx-0 flex items-center justify-center overflow-hidden">
                <img :src="company1Img" alt="" class="h-full w-full rounded-full object-cover" />
            </div>
            <div class="relative flex-grow">
                <p class="text-[18px] sm:text-[20px] font-[700] text-center sm:text-left capitalize pb-2 break-words w-full">{{ companyName }}
                </p>
                <div class="flex flex-wrap items-center justify-center sm:justify-start gap-2 text-[14px] font-[700] text-left capitalize text-[#0245A3]">
                    Hiring:
                    <img :src="hiringImg" alt="" class="h-[18px] w-[18px]" />
                    <span class="text-black font-[500]">{{ noOfHiring }}</span>
                </div>
                <p class="text-[14px] font-[500] text-center sm:text-left capitalize mt-1">{{ hiringMultipleRoles }}</p>

                <div class="grid grid-cols-2 md:grid-cols-3 gap-2 pt-3 justify-items-center sm:justify-items-start">
            <div class="text-[14px] font-[500] text-left capitalize text-[#5E5E5E] flex items-center gap-1"
                        v-for="(item, index) in jobFamily" :key="'fam-'+index">
                        <img :src="item.img" alt="" class="h-[16px] w-[16px] sm:h-[20px] sm:w-[20px]" />
                        <span class="truncate">{{ item.name }}</span>
                    </div>
                </div>
            </div>
        </div>
        <div class="flex flex-wrap gap-2 mb-4 justify-center sm:justify-start">
            <div class="text-center text-[13px] sm:text-[14px] font-[500] text-[#5E5E5E] capitalize py-1.5 px-3 sm:py-2 sm:px-4 rounded-[100px] border border-[#0245A3] inline-flex items-center gap-2 bg-[#0245A31A]"
                v-for="(value, index) in jobType" :key="'typ-'+index">
                <img :src="value.img" alt="" class="h-[16px] w-[16px] sm:h-[20px] sm:w-[20px]" />
                {{ value.name }}
            </div>
        </div>
        <button
            class="w-[calc(100%-2rem)] text-center text-[16px] sm:text-[17px] font-[700] text-[#0245A3] uppercase py-3 px-4 rounded-[10px] border border-[#0245A3] hover:bg-[#0245A3] hover:text-white absolute bottom-4 left-4 transition-colors">View
            Jobs</button>
    </div>
</template>

<script setup>
defineProps({
    company1Img: {
        type: String,
        default: ""
    },
    companyName: {
        type: String,
        default: ""
    },
    noOfHiring: {
        type: String,
        default: ""
    },
    hiringMultipleRoles: {
        type: String,
        default: ""
    },
    jobFamily: {
        type: Array,
        default: () => []
    },
    jobType: {
        type: Array,
        default: () => []
    },
    hiringImg: {
        type: String,
        default: ""
    }
})
</script>