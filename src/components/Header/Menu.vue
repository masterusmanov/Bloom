<template>
    <div @click="open" class="w-full h-[180vh] bg-black bg-opacity-20 top-0 right-0 left-0 flex justify-center items-center fixed z-50 border-none outline-none font-jost">
        <div class="w-full bg-[#141413] self-start max-w-screen-md max-h-screen-xl px-[16px] py-[11px]">
            <div class="flex items-center h-[60px]">
                <div class="w-[85%] flex items-center gap-2 md:w-[40%]">
                   <img src="../../assets/images/Logo.png" alt="Logo" class="w-[25px]">
                </div>
                <div @click="emitClose" class="ml-[25px] border flex items-center hover:rounded-b-full hover:rounded-tl-full">
                    <i class='bx bx-x text-[#E3E7F2] text-[36px]'></i>
                </div>
            </div>
            <ul class="text-sm text-gray-700 dark:text-gray-200 text-center px-[16px] py-[12px]" aria-labelledby="dropdownHoverButton">
                <li>
                    <a href="#about" @click="emitClose" class="text-[18px] block px-4 py-2 text-[#808288] hover:bg-black dark:hover:bg-[gray-600] hover:text-[#E3E7F2] font-rubik">{{$t('translation.navbar.one')}}</a>
                </li>
                <li>
                    <a href="#services" @click="emitClose" class="text-[18px] block px-4 py-2 text-[#808288] hover:bg-black dark:hover:bg-[gray-600] hover:text-[#E3E7F2] font-rubik">{{$t('translation.navbar.two')}}</a>
                </li>
                <li>
                    <a href="#portfolio" @click="emitClose" class="text-[18px] block px-4 py-2 text-[#808288] hover:bg-black dark:hover:bg-[gray-600] hover:text-[#E3E7F2] font-rubik">{{$t('translation.navbar.three')}}</a>
                </li>
                <li>
                    <a href="#client" @click="emitClose" class="text-[18px] block px-4 py-2 text-[#808288] hover:bg-black dark:hover:bg-[gray-600] hover:text-[#E3E7F2] font-rubik">{{$t('translation.navbar.four')}}</a>
                </li>
                <li>
                    <a href="#contact" @click="emitClose" class="text-[18px] block px-4 py-2 text-[#808288] hover:bg-black dark:hover:bg-[gray-600] hover:text-[#E3E7F2] font-rubik">{{$t('translation.navbar.five')}}</a>
                </li>
                <li class="my-[32px] ">
                    <p class="w-[92%] mx-4 font-[500] py-[10px] px-[20px] font-rubik text-[#E3E7F2] text-[20px]">+998 (90) 985 64 89</p>
                </li>
                <li class="my-[18px] text-[#808288] flex items-center justify-center gap-[20px] text-[26px]">
                    <a href="#"><i class='bx bxl-instagram border p-[14px] hover:bg-black hover:text-[#E3E7F2] group hover:rounded-b-full hover:rounded-tl-full' ></i></a>
                    <a href="#"><i class='bx bxl-behance border p-[14px] hover:bg-black hover:text-[#E3E7F2] group hover:rounded-b-full hover:rounded-tl-full'></i></a>
                    <a href="#"><i class='bx bxl-facebook border p-[14px] hover:bg-black hover:text-[#E3E7F2] group hover:rounded-b-full hover:rounded-tl-full'></i></a>
                    <a href="#"><i class='bx bxl-vk border p-[14px] hover:bg-black hover:text-[#E3E7F2] group hover:rounded-b-full hover:rounded-tl-full'></i></a>
                </li>
                <div class="flex gap-[16px] text-[20px] text-[#595A5E] mt-[30px]">
                    <a data-lang="en" @click="changeLanguage" class="hover:text-[#E3E7F2] cursor-pointer">EN</a>
                    <a data-lang="ru" @click="changeLanguage" class="hover:text-[#E3E7F2] cursor-pointer">RU</a>
                    <a data-lang="uz" @click="changeLanguage" class="hover:text-[#E3E7F2] cursor-pointer">UZ</a>
                </div>
            </ul>
        </div>
    </div>
</template>

<script setup>
import { defineEmits } from 'vue';
import { useI18n } from 'vue-i18n';
    
    const {t} = useI18n({useScope: 'global'});

    function changeLanguage(event) {
        const selectedLanguage = event.target.getAttribute('data-lang');
        console.log(selectedLanguage);
        localStorage.setItem("lang", selectedLanguage)
        window.location.reload()
    }

const emit = defineEmits(['close']);
function emitClose() {
  emit('close');
}
</script>

<style lang="scss" scoped>
</style>