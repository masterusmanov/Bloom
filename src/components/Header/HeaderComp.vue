<template>
    <header class="mt-[5px] lg:mt-[50px]">
        <div class="container mx-auto flex justify-between lg:justify-start lg:gap-[23px] items-center lg:items-start p-[16px] lg:p-0 font-jost">
            <div>
                <img src="../../assets/images/Logo.png" alt="" class="w-[25px] lg:w-[43px]">
            </div>
            <div class="hidden lg:grid font-[500] text-[30px]">
                <router-link to="#about" class="text-[#808288] hover:text-[#E3E7F2]">{{$t('translation.navbar.one')}}</router-link>
                <router-link to="#about" class="text-[#808288] hover:text-[#E3E7F2]">{{$t('translation.navbar.two')}}</router-link>
                <router-link to="#about" class="text-[#808288] hover:text-[#E3E7F2]">{{$t('translation.navbar.three')}}</router-link>
                <router-link to="#about" class="text-[#808288] hover:text-[#E3E7F2]">{{$t('translation.navbar.four')}}</router-link>
                <router-link to="#about" class="text-[#808288] hover:text-[#E3E7F2]">{{$t('translation.navbar.five')}}</router-link>
                <div class="flex gap-[16px] text-[20px] text-[#595A5E] mt-[30px]">
                    <option value="en" class="hover:text-[#E3E7F2]">EN</option>
                    <option value="ru" class="hover:text-[#E3E7F2]">RU</option>
                    <option value="uz" class="hover:text-[#E3E7F2]">UZ</option>
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
        const selectedLanguage = event.target.value;
        console.log(selectedLanguage);
        localStorage.setItem("lang", selectedLanguage)
        window.location.reload()
    }
</script>

<style lang="scss" scoped>

</style>