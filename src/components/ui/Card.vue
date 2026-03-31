<template>
    <div class="border-1 border-[#C6C6C6] rounded-[12px] p-4 hover:border-[#0245A3] relative h-[320px]">
        <div class="grid grid-cols-[20%_auto] gap-3 pb-4">
            <div class="border-3 border-[#0245A3] rounded-[100px] p-1 w-[110px]">
                <img :src="company1Img" alt="" class="h-[100px] w-auto rounded-full object-cover" />
            </div>
            <div class="relative left-[0px]">
                <p class="text-[20px] font-[700] text-left capitalize pb-2 ellipsis w-[350px]">{{ companyName }}
                </p>
                <p class="flex items-center gap-2 text-[14px] font-[700] text-left capitalize text-[#0245A3]">
                    Hiring:
                    <img :src="hiringImg" alt="" class="h-[18px] w-[18px]" />
                <p class="text-black font-[500]">{{ noOfHiring }}</p>
                </p>
                <p class="text-[14px] font-[500] text-left capitalize">{{ hiringMultipleRoles }}</p>

                <div class="grid grid-cols-3 gap-3 pt-2">
                    <div class="text-[14px] font-[500] text-left capitalize text-[#5E5E5E] flex items-center gap-2"
                        v-for="(item, index) in jobFamily">
                        <img :src="item.img" alt="" class="h-[20px] w-[20px]" />
                        {{ item.name }}
                    </div>
                </div>
            </div>
        </div>
        <div class="flex flex-wrap gap-2 mb-4">
            <div class="text-center text-[14px] font-[500] text-[#5E5E5E] capitalize py-2 px-4 rounded-[100px] border-1 border-[#0245A3] inline-flex items-center gap-2 bg-[#0245A31A]"
                v-for="(value, index) in jobType">
                <img :src="value.img" alt="" class="h-[20px] w-[20px]" />
                {{ value.name }}
            </div>
        </div>
        <button
            class="w-[94%] text-center text-[17px] font-[700] text-[#0245A3] uppercase py-3 px-4 rounded-[10px] border-1 border-[#0245A3] hover:bg-[#0245A3] hover:text-white absolute bottom-4">View
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