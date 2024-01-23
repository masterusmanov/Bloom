<script setup>
import SectionOne from '../components/SectionOne/SectionOne.vue'
import SectionTwo from '../components/SectionOne/SectionTwo.vue'
import SectionThree from '../components/SectionOne/SectionThree.vue'
import SectionFour from '../components/SectionOne/SectionFour.vue'
import CardClient from '../components/CardClient/CardClient.vue';
import SectionFive from '../components/SectionOne/SectionFive.vue';
</script>

<template>
  <main>
    <SectionOne class=""/>
    <SectionTwo/>
    <img src="../assets/images/background/service.png" alt="" class="absolute w-[125px] lg:w-[250px] xl:w-[400px] mt-[50px] ml-[170px] lg:ml-[700px] lg:mt-[150px] xl:ml-[800px] 2xl:ml-[1150px] 2xl:mt-[250px]">
    <SectionThree/>
    <img src="../assets/images/background/plan.svg" alt="" class="absolute w-[70%] lg:w-[50%] mt-[50px] ml-[15%] lg:ml-[25%] lg:mt-[150px] 2xl:mt-[200px]">
    <SectionFour/>
    <CardClient/>
    <img src="../assets/images/background/Group2.svg" alt="" class="absolute w-[70%] lg:w-[50%] mt-[50px] ml-[15%] lg:ml-[25%] lg:mt-[150px] 2xl:mt-[200px]">
    <SectionFive/>
  </main>
</template>
