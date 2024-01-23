<script setup>
  import { ref, onMounted } from "vue";
  import SectionOne from '../components/SectionOne/SectionOne.vue'
  import SectionTwo from '../components/SectionOne/SectionTwo.vue'
  import SectionThree from '../components/SectionOne/SectionThree.vue'
  import SectionFour from '../components/SectionOne/SectionFour.vue'
  import CardClient from '../components/CardClient/CardClient.vue';
  import SectionFive from '../components/SectionOne/SectionFive.vue';
  import CardClientTwo from '../components/CardClient/CardClientTwo.vue'
  import Footer from '../components/Footer/Footer.vue';
  import Modal from '../components/Modal/Modal.vue'
  import ModalOne from '../components/Modal/ModalOne.vue'

  const modal2 = ref(false);

  const open1 = () => {
      modal2.value = true;
  };
  
  const close2 = () => {
      modal2.value = false;
  };

</script>

<template>
  <main>
    <div class="container mx-auto">
      <SectionOne class=""/>
      <SectionTwo/>
      <img src="../assets/images/background/service.png" alt="" class="absolute w-[100px] lg:w-[220px] xl:w-[300px] mt-[70px] ml-[190px] lg:ml-[750px] lg:mt-[150px] xl:ml-[900px] 2xl:ml-[1100px] 2xl:mt-[250px]">
      <SectionThree/>
      <img src="../assets/images/background/plan.svg" alt="" class="absolute w-[197px] lg:w-[704px] mx-[65px] lg:mx-[170px] xl:mx-[300px] 2xl:mx-[400px] mt-[50px] lg:mt-[150px] 2xl:mt-[200px]">
      <SectionFour/>
      <CardClient/>
      <img src="../assets/images/background/Group2.svg" alt="" class="absolute w-[197px] lg:w-[704px] mx-[65px] lg:mx-[170px] xl:mx-[300px] 2xl:mx-[400px] mt-[50px] lg:mt-[150px] 2xl:mt-[200px]">
      <SectionFive/>
      <CardClientTwo/>
      <div @click="open1">
        <Modal class="absolute w-[100px] lg:w-[210px] xl:w-[250px] lg:h-[210px] xl:h-[250px] border grid justify-between p-[8px] lg:p-[16px] mt-[125px] ml-[200px] bg-black border-[#E3E7F2] cursor-pointer lg:mt-[100px] xl:ml-[1000px] 2xl:ml-[1200px]"/>
      </div>
      <ModalOne  @close="close2" v-if="modal2"/>
      <Footer/>
    </div>
  </main>
</template>

<style lang="scss" scoped>
  *{
    scroll-behavior: smooth;
  }
</style>