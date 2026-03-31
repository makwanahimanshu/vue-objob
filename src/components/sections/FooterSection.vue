<template>
    <section class="w-full py-12 font-poppins">
        <!-- Full width border -->
        <hr class="border-t border-[#0245A3] w-full pb-8" />

        <div class="max-w-[1240px] mx-auto px-6">
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-5 gap-8 lg:gap-4 text-black leading-6 mt-2 text-center sm:text-left">
                <div>
                    <img :src="logo" alt="" class="h-[110px] w-[80px]" />
                </div>
                <div>
                    <h3 class="text-[16px] font-[600] text-black capitalize pb-4">Employer</h3>
                    <p>Post a Job</p>
                    <p>Post a Walkin</p>
                    <p>Register</p>
                    <p>Login</p>
                </div>
                <div>
                    <h3 class="text-[16px] font-[600] text-black capitalize pb-4">Job Seeker</h3>
                    <p>Job Seeker</p>
                    <p>Register</p>
                    <p>Search Jobs</p>
                    <p>Blogs</p>
                    <p>Login</p>
                </div>
                <div>
                    <h3 class="text-[16px] font-[600] text-black capitalize pb-4">Information</h3>
                    <p class="cursor-pointer hover:text-[#0245A3] mb-1 hover:underline">About Us</p>
                    <p class="cursor-pointer hover:text-[#0245A3] mb-1 hover:underline">Contact Us</p>
                </div>
                <div>
                    <h3 class="text-[16px] font-[600] text-black capitalize pb-4">Available on</h3>
                    <div class="flex justify-center sm:justify-start gap-6 pb-2">
                        <div class="flex flex-col items-center">
                            <img :src="googlePlayImg" alt="" class="h-[40px] w-auto pb-1" />
                            <p class="text-[14px] font-[500]">iOS</p>
                        </div>
                        <div class="flex flex-col items-center">
                            <img :src="appStoreImg" alt="" class="h-[40px] w-auto pb-1" />
                            <p class="text-[14px] font-[500]">Playstore</p>
                        </div>
                    </div>
                    <h3 class="text-[16px] font-[600] text-black capitalize pb-4 pt-6">Social media links</h3>
                    <div class="flex justify-center sm:justify-start gap-4">
                        <div class="cursor-pointer hover:opacity-80 transition-opacity">
                            <img :src="linkedinImg" alt="" class="h-[30px] w-[30px]" />
                        </div>
                        <div class="cursor-pointer hover:opacity-80 transition-opacity">
                            <img :src="facebookImg" alt="" class="h-[32px] w-[32px]" />
                        </div>
                        <div class="cursor-pointer hover:opacity-80 transition-opacity">
                            <img :src="twitterImg" alt="" class="h-[33px] w-[33px]" />
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue'
import logo_footer from '@/assets/images/logo_footer.jpg'
import google_play from '@/assets/images/apple.jpg'
import app_store from '@/assets/images/playstore.jpg'
import facebook from '@/assets/images/facebook.png'
import linkedin from '@/assets/images/linkedin.png'
import twitter from '@/assets/images/twitter.png'

const logo = ref(logo_footer)
const googlePlayImg = ref(google_play)
const appStoreImg = ref(app_store)
const facebookImg = ref(facebook)
const linkedinImg = ref(linkedin)
const twitterImg = ref(twitter)


</script>
