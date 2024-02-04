<template>
    <div class="container">
      <!-- <div class="faders">
        <div class="left"></div>
        <div class="right"></div>
      </div> -->
    
      <div class="items ">
        <div class="entry w-[200px] lg:w-[500px] xl:w-[750px]">
          <h1 class="text-[#E3E7F2] font-jost font-[600] text-[50px] lg:text-[100px] xl:text-[150px]">{{ $t('translation.service') }}</h1>
        </div>
        <div class="entry w-[200px] lg:w-[500px] xl:w-[750px]">
          <h1 class="text-[#E3E7F2] font-jost font-[600] text-[50px] lg:text-[100px] xl:text-[150px]">{{ $t('translation.service') }}</h1>
        </div>
        <div class="entry w-[200px] lg:w-[500px] xl:w-[750px]">
          <h1 class="text-[#E3E7F2] font-jost font-[600] text-[50px] lg:text-[100px] xl:text-[150px]">{{ $t('translation.service') }}</h1>
        </div>
        <div class="entry w-[200px] lg:w-[500px] xl:w-[750px]">
          <h1 class="text-[#E3E7F2] font-jost font-[600] text-[50px] lg:text-[100px] xl:text-[150px]">{{ $t('translation.service') }}</h1>
        </div>
        <div class="entry w-[200px] lg:w-[500px] xl:w-[750px]">
          <h1 class="text-[#E3E7F2] font-jost font-[600] text-[50px] lg:text-[100px] xl:text-[150px]">{{ $t('translation.service') }}</h1>
        </div>
        <div class="entry w-[200px] lg:w-[500px] xl:w-[750px]">
          <h1 class="text-[#E3E7F2] font-jost font-[600] text-[50px] lg:text-[100px] xl:text-[150px]">{{ $t('translation.service') }}</h1>
        </div>
        <div class="entry w-[200px] lg:w-[500px] xl:w-[750px]">
          <h1 class="text-[#E3E7F2] font-jost font-[600] text-[50px] lg:text-[100px] xl:text-[150px]">{{ $t('translation.service') }}</h1>
        </div>
        <div class="entry w-[200px] lg:w-[500px] xl:w-[750px]">
          <h1 class="text-[#E3E7F2] font-jost font-[600] text-[50px] lg:text-[100px] xl:text-[150px]">{{ $t('translation.service') }}</h1>
        </div>
      </div>
    </div>

  </template>
    
    <script setup>
    
    </script>
    
    <style lang="scss" scoped>
    @import url("https://fonts.googleapis.com/css?family=Muli:400,700&display=swap");



    .container {
      width: 100%;
      overflow-x: hidden;
      position: relative;
    }

    .items {
      display: flex;
      gap: 44px;
      align-items: center;
      width: fit-content;
      width: max-content;
      animation: carouselAnim 30s infinite alternate linear;
      overflow-x: auto;
    }

    .entry {
      display: flex;
      align-items: center;
      flex-direction: column;
      position: relative;
      margin: 1em;
      padding: 0.5em;
    }

    @media only screen and (max-width: 768px) {
      .items {
        animation: carouselAnim 20s infinite alternate linear;
        overflow: hidden;
      }

      @keyframes carouselAnim {
        from {
          transform: translate(0, 0);
        }
        to {
          transform: translate(calc(-100% + (2 * 300px)));
        }
      }
    }

    .entry p {
      text-align: center;
      padding: 1em;
    }

    .name {
      font-weight: bold;
    }

    @keyframes carouselAnim {
      from {
        transform: translate(0, 0);
      }
      to {
        transform: translate(calc(-100% + (5 * 300px)));
      }
    }

    .container .faders {
      width: 100%;
      position: absolute;
      height: 100%;
    }

    .faders .right,
    .faders .left {
      width: 15%;
      height: 100%;
      position: absolute;
      z-index: 200;
    }

    .right {
      right: 0;
    }
</style>