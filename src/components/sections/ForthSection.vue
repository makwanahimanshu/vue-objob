<template>
  <section class="w-full py-12 font-poppins">
    <div class="max-w-[1240px] mx-auto px-6">
      <div class="flex flex-col md:flex-row justify-between items-start md:items-center gap-6 md:gap-0">
        <div class="leading-tight">
          <h1 class="text-[#0245A3] text-[28px] md:text-[40px] font-[1000] text-left uppercase pb-2 md:pb-8 tracking-[0.50px]">
            {{ getTopCompanies }}
          </h1>
          <p class="text-black text-[18px] md:text-[25px] font-[500] text-left capitalize pb-0 md:pb-8">
            {{ organizationsActivelyHiring }}
          </p>
        </div>
        <div class="flex items-center w-full md:w-auto mt-4 md:mt-0 justify-start md:justify-end">
          <button
            class="bg-[#0245A3] text-white px-6 md:px-8 py-3 md:py-4 rounded-[12px] shadow-[0_5px_10px_rgba(19,99,223,.25)] hover:bg-white border hover:border-[#0245A3] hover:text-[#0245A3] uppercase cursor-pointer font-[700] transition-colors text-sm md:text-base">
            {{ viewAll }}
          </button>
        </div>
      </div>



      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 text-black leading-6 mt-8 md:mt-2">
        <!-- card -->
        <div class="border-1 border-[#C6C6C6] rounded-[12px] hover:border-[#0245A3] h-auto pb-4 transition-all"
          v-for="(value, key) in myObject">


          <div class="rounded-[12px] 
            hover:border-[#0245A3] 
            overflow-hidden">

            <!-- Top Full Width Image -->
            <div class="w-full h-[100px] overflow-hidden">
              <img :src="value.topCompany1Img" class="w-full h-full object-cover" />
            </div>

            <!-- Card Content -->
            <div class="p-1">
              <!-- Your existing grid content here -->


              <div class="relative">
                <div class="flex items-start gap-4">

                  <!-- Company Logo -->
                  <div class="border-4 border-[#0245A3] rounded-full 
                    w-[90px] h-[90px] lg:w-[130px] lg:h-[130px] 
                    overflow-hidden flex-shrink-0
                    absolute -top-[45px] lg:-top-[60px] left-[12px] lg:left-[8px] bg-white">
                    <img :src="value.company1Img" class="w-full h-full object-cover" />
                  </div>

                  <!-- Content -->
                  <div class="pl-[115px] lg:pl-[145px] pr-2 w-full pt-1 lg:pt-0">
                    <p class="text-[15px] lg:text-[16px] font-[700] capitalize break-words w-full">
                      {{ value.companyName }}
                    </p>

                    <div class="flex items-center gap-2 text-[16px] font-[700] text-[#0245A3]">
                      Hiring:
                      <img :src="hiringImg" class="h-[18px] w-[20px]" />
                      <span class="text-black font-[500]">
                        {{ value.noOfHiring }}
                      </span>
                    </div>

                    <p class="text-[14px] font-[500] text-[#5E5E5E] capitalize">
                      {{ value.hiringMultipleRoles }}
                    </p>
                  </div>



                </div>
              </div>

              <p class="text-[14px] font-[400] text-black px-3 py-4">Purus sit id mus scelerisque duis pulvinar. Enim
                lacinia risus neque egestas tempor. </p>


              <div class="grid grid-cols-3 gap-1 lg:gap-3 pt-2 px-3">
                <div class="text-[12px] lg:text-[14px] font-[500] text-left capitalize text-[#5E5E5E] flex items-center gap-1 lg:gap-2" v-for="(item, index) in value.jobFamily">
                    <img :src="item.img" alt="" class="h-[18px] w-[18px] lg:h-[22px] lg:w-[22px]" />
                    <span class="truncate">{{ item.name }}</span>

                  </div>
              </div>

              <div class="grid grid-cols-3 gap-1 lg:gap-3 px-3">
                <div class="text-[12px] lg:text-[14px] font-[500] capitalize text-[#5E5E5E] flex items-center gap-1 lg:gap-2 ml-5 lg:ml-7" v-for="(item, index) in value.jobFamily">
                    <span class="truncate">{{ item.name }}</span>
                  </div>
              </div>

              <div class="px-3">
                <button 
                  @mouseenter="isHover = true"
                  @mouseleave="isHover = false"
                  class="flex items-center justify-between gap-2 w-[100%] text-center text-[17px] font-[700] text-[#0245A3] uppercase py-3 px-6 rounded-[10px] border-1 border-[#0245A3] hover:bg-[#0245A3] hover:text-white cursor-pointer mt-[25px]">
                  Upload your resume
                  <img :src="isHover ? uploadImg2 : uploadImg" class="h-[18px] w-[20px]" />
                </button>
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
import topCompany1 from '@/assets/images/topcompany1.jpg'
import topCompany2 from '@/assets/images/topcompany2.jpg'
import topCompany3 from '@/assets/images/topcompany3.jpg'
import topCompany4 from '@/assets/images/topcompany4.jpg'
import company1 from '@/assets/images/company1.png'
import company2 from '@/assets/images/company2.png'
import company3 from '@/assets/images/company3.png'
import company4 from '@/assets/images/company4.png'
import hiring from '@/assets/images/people.svg'
import location from '@/assets/images/location.svg'
import fulltime from '@/assets/images/fulltime.svg'
import urgentlyHiring from '@/assets/images/urgently_hiring.svg'
import wfhImage from '@/assets/images/happy.svg'
import flexibleTiming from '@/assets/images/flexible_timing.svg'
import upload from '@/assets/images/upload.svg'
import upload2 from '@/assets/images/upload2.svg'

const isHover = ref(false)

let getTopCompanies = ref('Top Companies')
let organizationsActivelyHiring = ref('Organizations actively hiring')
let viewAll = ref('View All')

let company1Img = ref(company1)
let company2Img = ref(company2)
let company3Img = ref(company3)
let company4Img = ref(company4)

let topCompany1Img = ref(topCompany1)
let topCompany2Img = ref(topCompany2)
let topCompany3Img = ref(topCompany3)
let topCompany4Img = ref(topCompany4)

let hiringImg = ref(hiring)
let locationImg = ref(location)
let fulltimeImg = ref(fulltime)
let urgentlyHiringImg = ref(urgentlyHiring)
let wfhImg = ref(wfhImage)
let flexibleTimingImg = ref(flexibleTiming)
let uploadImg = ref(upload)
let uploadImg2 = ref(upload2)

let myObject = ref([
  {
    topCompany1Img: topCompany1Img,
    company1Img: company1Img,
    companyName: 'Nike Jordan',
    noOfHiring: 40,
    hiringMultipleRoles: 'Hiring Multiple job roles',
    jobFamily: [
      {
        "name": 'Location',
        "img": locationImg
      },
      {
        "name": 'Staff',
        "img": fulltimeImg
      },
      {
        "name": 'Job Type',
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
    topCompany1Img: topCompany2Img,
    company1Img: company2Img,
    companyName: 'cocacola Pvt. ltd.',
    noOfHiring: 40,
    hiringMultipleRoles: 'Hiring Multiple job roles',
    jobFamily: [
      {
        "name": 'Location',
        "img": locationImg
      },
      {
        "name": 'Staff',
        "img": fulltimeImg
      },
      {
        "name": 'Job Type',
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
    topCompany1Img: topCompany3Img,
    company1Img: company3Img,
    companyName: 'TikTok incorp',
    noOfHiring: 40,
    hiringMultipleRoles: 'Hiring Multiple job roles',
    jobFamily: [
      {
        "name": 'Location',
        "img": locationImg
      },
      {
        "name": 'Staff',
        "img": fulltimeImg
      },
      {
        "name": 'Job Type',
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
    topCompany1Img: topCompany4Img,
    company1Img: company4Img,
    companyName: 'Not a very good logo TBH pvt. ltd.',
    noOfHiring: 40,
    hiringMultipleRoles: 'Hiring Multiple job roles',
    jobFamily: [
      {
        "name": 'Location',
        "img": locationImg
      },
      {
        "name": 'Staff',
        "img": fulltimeImg
      },
      {
        "name": 'Job Type',
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
