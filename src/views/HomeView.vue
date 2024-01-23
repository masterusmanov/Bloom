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
      <img src="../assets/images/background/service.png" alt="" class="absolute w-[125px] lg:w-[250px] xl:w-[400px] mt-[50px] ml-[170px] lg:ml-[700px] lg:mt-[150px] xl:ml-[800px] 2xl:ml-[1000px] 2xl:mt-[250px]">
      <SectionThree/>
      <img src="../assets/images/background/plan.svg" alt="" class="absolute w-[70%] lg:w-[50%] mt-[50px] ml-[15%] lg:ml-[25%] lg:mt-[150px] 2xl:mt-[200px]">
      <SectionFour/>
      <CardClient/>
      <img src="../assets/images/background/Group2.svg" alt="" class="absolute w-[70%] lg:w-[50%] mt-[50px] ml-[15%] lg:ml-[25%] lg:mt-[150px] 2xl:mt-[200px]">
      <SectionFive/>
      <CardClientTwo/>
      <div @click="open1">
        <Modal class="absolute w-[100px] lg:w-[210px] xl:w-[250px] lg:h-[210px] xl:h-[250px] border grid justify-between p-[8px] lg:p-[16px] mt-[125px] ml-[60%] bg-black border-[#E3E7F2] cursor-pointer lg:mt-[100px] xl:ml-[1000px] 2xl:ml-[1200px]"/>
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