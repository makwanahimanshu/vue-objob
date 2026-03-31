<template>
  <section class="w-full py-12 font-poppins">
    <div class="max-w-[1240px] mx-auto px-6">
      <div class="flex justify-between items-center">
        <div class="leading-3">
          <h1 class="text-[#0245A3] text-[40px] font-[1000] text-left uppercase pb-8 tracking-[0.50px]">
            {{ getHired }}
          </h1>
          <p class="text-black text-[25px] font-[500] text-left capitalize pb-8">
            {{ sponsoredCompanies }}
          </p>
        </div>
        <div class="flex items-center gap-4">
          <div class="border border-[#0245A3] rounded-[50%] bg-white cursor-pointer p-4">
            <img :src="leftArrowImg" alt="" class="h-[25px] w-[25px]" />
          </div>
          <div class="border border-[#0245A3] rounded-[50%] bg-[#0245A3] cursor-pointer p-4">
            <img :src="rightArrowImg" alt="" class="h-[25px] w-[25px]" />
          </div>
          <button
            class="bg-[#0245A3] text-white px-8 py-4 rounded-[12px] shadow-[0_5px_10px_rgba(19,99,223,.25)] hover:bg-white hover:border-[#0245A3] border-1 hover:text-[#0245A3] uppercase cursor-pointer font-[700]">
            {{ viewBtn }}
          </button>
        </div>
      </div>
      <div class="grid grid-cols-2 gap-6 text-black leading-6 mt-2">

        <!-- card -->
        <Card v-for="(value, key) in myObject" :key="key" :company1Img="value.company1Img"
          :companyName="value.companyName" :noOfHiring="value.noOfHiring"
          :hiringMultipleRoles="value.hiringMultipleRoles" :jobFamily="value.jobFamily" :jobType="value.jobType"
          :hiringImg="hiringImg" />
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import leftArrow from '@/assets/images/left_arrow.svg'
import rightArrow from '@/assets/images/right_arrow.svg'
import company1 from '@/assets/images/company1.png'
import company2 from '@/assets/images/company2.png'
import company3 from '@/assets/images/company3.png'
import company4 from '@/assets/images/company4.png'
import hiring from '@/assets/images/person.svg'
import location from '@/assets/images/location.svg'
import fulltime from '@/assets/images/fulltime.svg'
import urgentlyHiring from '@/assets/images/urgently_hiring.svg'
import wfhImage from '@/assets/images/happy.svg'
import flexibleTiming from '@/assets/images/flexible_timing.svg'
import Card from '../ui/Card.vue'

let getHired = ref('Get Hired')
let sponsoredCompanies = ref('Sponsored companies')
let viewBtn = ref('View All')

let leftArrowImg = ref(leftArrow)
let rightArrowImg = ref(rightArrow)
let company1Img = ref(company1)
let company2Img = ref(company2)
let company3Img = ref(company3)
let company4Img = ref(company4)
let hiringImg = ref(hiring)
let locationImg = ref(location)
let fulltimeImg = ref(fulltime)
let urgentlyHiringImg = ref(urgentlyHiring)
let wfhImg = ref(wfhImage)
let flexibleTimingImg = ref(flexibleTiming)

let myObject = ref([
  {
    company1Img: company1Img,
    companyName: 'Nike Jordan',
    noOfHiring: 40,
    hiringMultipleRoles: 'Hiring Multiple job roles',
    jobFamily: [
      {
        "name": 'Mumbai',
        "img": locationImg
      },
      {
        "name": 'Fulltime',
        "img": fulltimeImg
      },
      {
        "name": 'Urgently Hiring',
        "img": urgentlyHiringImg
      }
    ],
    jobType: [
      {
        "name": 'Mumbai',
        "img": locationImg
      },
      {
        "name": 'Wfh',
        "img": wfhImg
      },
      {
        "name": 'Mumbai',
        "img": locationImg
      },
      {
        "name": 'Flexible timing',
        "img": flexibleTimingImg
      }
    ],

  },
  {
    company1Img: company2Img,
    companyName: 'cocacola Pvt. ltd.',
    noOfHiring: 40,
    hiringMultipleRoles: 'Hiring Multiple job roles',
    jobFamily: [
      {
        "name": 'Mumbai',
        "img": locationImg
      },
      {
        "name": 'Fulltime',
        "img": fulltimeImg
      },
      {
        "name": 'Urgently Hiring',
        "img": urgentlyHiringImg
      }
    ],
    jobType: [
      {
        "name": 'Mumbai',
        "img": locationImg
      },
      {
        "name": 'Wfh',
        "img": wfhImg
      },
      {
        "name": 'Flexible timing',
        "img": flexibleTimingImg
      },
      {
        "name": 'Mumbai',
        "img": locationImg
      },
      {
        "name": 'Wfh',
        "img": wfhImg
      },
      {
        "name": 'Flexible timing',
        "img": flexibleTimingImg
      }
    ],
  },
  {
    company1Img: company3Img,
    companyName: 'TikTok incorp',
    noOfHiring: 40,
    hiringMultipleRoles: 'Hiring Multiple job roles',
    jobFamily: [
      {
        "name": 'Mumbai',
        "img": locationImg
      },
      {
        "name": 'Fulltime',
        "img": fulltimeImg
      },
      {
        "name": 'Urgently Hiring',
        "img": urgentlyHiringImg
      }
    ],
    jobType: [
      {
        "name": 'Mumbai',
        "img": locationImg
      },
      {
        "name": 'Wfh',
        "img": wfhImg
      },
      {
        "name": 'Flexible timing',
        "img": flexibleTimingImg
      },
      {
        "name": 'Mumbai',
        "img": locationImg
      },
      {
        "name": 'Wfh',
        "img": wfhImg
      },
      {
        "name": 'Flexible timing',
        "img": flexibleTimingImg
      }
    ],
  },
  {
    company1Img: company4Img,
    companyName: 'Not a very good logo TBH pvt. ltd.',
    noOfHiring: 40,
    hiringMultipleRoles: 'Hiring Multiple job roles',
    jobFamily: [
      {
        "name": 'Mumbai',
        "img": locationImg
      },
      {
        "name": 'Fulltime',
        "img": fulltimeImg
      },
      {
        "name": 'Urgently Hiring',
        "img": urgentlyHiringImg
      }
    ],
    jobType: [
      {
        "name": 'Mumbai',
        "img": locationImg
      },
      {
        "name": 'Wfh',
        "img": wfhImg
      },
      {
        "name": 'Mumbai',
        "img": locationImg
      },
      {
        "name": 'Flexible timing',
        "img": flexibleTimingImg
      }
    ],
  }
])

</script>
