<template>
    <header class="mt-[5px] lg:mt-[50px]">
        <div class="container mx-auto flex justify-between lg:justify-start lg:gap-[23px] items-center lg:items-start p-[16px] lg:p-0 font-jost">
            <div>
                <img src="../../assets/images/Logo.png" alt="" class="w-[25px] lg:w-[43px]">
            </div>
            <div class="hidden lg:grid font-[500] text-[30px]">
                <a href="#about" class="text-[#808288] hover:text-[#E3E7F2] cursor-pointer">{{$t('translation.navbar.one')}}</a>
                <a href="#services" class="text-[#808288] hover:text-[#E3E7F2] cursor-pointer">{{$t('translation.navbar.two')}}</a>
                <a href="#portfolio" class="text-[#808288] hover:text-[#E3E7F2] cursor-pointer">{{$t('translation.navbar.three')}}</a>
                <a href="#client" class="text-[#808288] hover:text-[#E3E7F2] cursor-pointer">{{$t('translation.navbar.four')}}</a>
                <a href="#contact" class="text-[#808288] hover:text-[#E3E7F2] cursor-pointer">{{$t('translation.navbar.five')}}</a>                
                <div class="flex gap-[16px] text-[20px] text-[#595A5E] mt-[30px] cursor-pointer">
                    <a data-lang="en" @click="changeLanguage" class="hover:text-[#E3E7F2] cursor-pointer">EN</a>
                    <a data-lang="ru" @click="changeLanguage" class="hover:text-[#E3E7F2] cursor-pointer">RU</a>
                    <a data-lang="uz" @click="changeLanguage" class="hover:text-[#E3E7F2] cursor-pointer">UZ</a>
                </div>
            </div>
        </div>
    </header>
</template>

<script setup>
    import '../../assets/main.css';
    import { ref, onMounted } from "vue";
    import { useRouter } from "vue-router";
    import { useI18n } from 'vue-i18n';
    
    const {t} = useI18n({useScope: 'global'});

    function changeLanguage(event) {
        const selectedLanguage = event.target.getAttribute('data-lang');
        console.log(selectedLanguage);
        localStorage.setItem("lang", selectedLanguage)
        window.location.reload()
    }
</script>

<style lang="scss" scoped>

</style>