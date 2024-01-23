<template>
    <section id="services" class="mt-[372px] lg:mt-[116px]">
        <div class="container mx-auto">
            <h1 class="text-[#E3E7F2] font-jost font-[700] w-[85%] lg:w-[50%] mx-auto px-[16px] lg:px-0 text-[18px] lg:text-[28px] xl:text-[40px]">{{ $t('translation.sectionTwo.one') }} <span class="text-[#454648]">{{ $t('translation.sectionTwo.two') }}</span></h1>
            <div class="absolute w-full my-[70px] lg:my-[75px] xl:my-[100px]">
                <img src="../../assets/images/background/Group.svg" alt="" class="w-[197px] lg:w-[50%] mx-auto lg:mx-[25%] 2xl:mx-[17%]">
            </div>
            <TextCarusel class="mt-[90px] lg:mt-[200px] xl:mt-[220px] 2xl:mt-[350px]"/>
        </div>
    </section>
</template>

<script setup>
    import TextCarusel from './TextCarusel.vue'
</script>

<style lang="scss" scoped>

</style>