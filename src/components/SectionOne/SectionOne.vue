<template>
    <section id="about">
      <div @click="open1">
        <Modal class="absolute w-[100px] lg:w-[210px] xl:w-[250px] lg:h-[210px] xl:h-[250px] border grid justify-between p-[8px] lg:p-[16px] mt-[270px] ml-[50px] bg-black border-[#E3E7F2] cursor-pointer lg:mt-[320px] lg:ml-[280px] xl:mt-[320px] xl:ml-[400px] 2xl:mt-[400px] 2xl:ml-[565px] hover:rounded-b-full hover:rounded-tl-full"/>
      </div>
      <ModalOne  @close="close2" v-if="modal2"/>
      <div class="container mx-auto hidden lg:flex ">
        <div>
          <HeaderComp/>
        </div>
        <div class="lg:ml-[200px] xl:ml-[390px] 2xl:ml-[550px]">
          <h1 class="text-[#E3E7F2] font-[600] lg:text-[70px] xl:text-[80px] 2xl:text-[100px] font-jost absolute lg:ml-[250px] lg:mt-[70px] xl:ml-[255px] xl:mt-[70px] 2xl:ml-[250px]">Bloom <br>Architechture</h1>
          <img src="../../assets/images/background/logo.svg" alt="logo" class="lg:w-[700px] xl:w-[750px] 2xl:w-[900px]">
        </div>
      </div>
      <div class="lg:hidden ">
          <img src="../../assets/images/background/Vector.svg" alt="logo" class=" absolute w-[300px] ml-[16%]">
          <div class="absolute mt-[100px]">
              <h1 class="text-[#E3E7F2] font-[600] text-[40px] font-jost  ml-[19%]">Bloom <br>Architechture</h1>
            </div>
            <Header class="relative"/>
        </div>
    </section>
  </template>

<script setup>
    import { ref, onMounted } from "vue";
    import Header from '../Header/Header.vue'
    import HeaderComp from '../Header/HeaderComp.vue'
    import Modal from '../Modal/Modal.vue'
    import ModalOne from '../Modal/ModalOne.vue'

    const modal2 = ref(false);

    const open1 = () => {
        modal2.value = true;
    };
    
    const close2 = () => {
        modal2.value = false;
    };
</script>

<style lang="scss" scoped>

</style>