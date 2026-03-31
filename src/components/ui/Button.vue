<template>
    <div class="hidden lg:flex lg:flex-1 justify-end">
        <button class="bg-[#0245A3] text-white px-[30px] py-2 rounded-[15px] font-[600] cursor-pointer hover:bg-white hover:border-[#0245A3] border-1 hover:text-[#0245A3]">{{ text }}</button>
    </div>
</template>


<script setup>
defineProps({
  text: {
    type: String,
    default: "Button"
  }
})

</script>
