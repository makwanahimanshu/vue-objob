<template>
    <section class="w-full py-12 font-poppins">
        <!-- Full width border -->
        <hr class="border-t border-[#0245A3] w-full pb-8" />

        <div class="max-w-[1240px] mx-auto">
            <div class="grid grid-cols-7 gap-1 text-black leading-6 mt-2">
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
                    <p>About Us</p>
                    <p>Contact Us</p>
                </div>
                <div>

                </div>
                <div>

                </div>
                <div>
                    <h3 class="text-[16px] font-[600] text-black capitalize pb-4">Available on</h3>
                    <div class="grid grid-cols-2">
                        <div>
                            <img :src="googlePlayImg" alt="" class="h-[50px] w-[50px] pb-1" />
                            <p class="text-[15px] font-[400]">ISO</p>
                        </div>
                        <div>
                            <img :src="appStoreImg" alt="" class="h-[50px] w-[50px] pb-1" />
                            <p class="text-[15px] font-[400]">Playstore</p>
                        </div>
                    </div>
                    <h3 class="text-[16px] font-[600] text-black capitalize pb-4 pt-3">Social media links</h3>
                    <div class="grid grid-cols-3">
                        <div>
                            <img :src="linkedinImg" alt="" class="h-[30px] w-[30px] pb-1" />
                        </div>
                        <div>
                            <img :src="facebookImg" alt="" class="h-[32px] w-[32px] pb-1" />
                        </div>
                        <div>
                            <img :src="twitterImg" alt="" class="h-[33px] w-[33px] pb-1" />
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
