<template>
    <div class=" container mx-auto relative mt-[130px] lg:mt-[250px] 2xl:mt-[350px]">
        <div class="slides-container  flex snap-x snap-mandatory overflow-hidden overflow-x-auto space-x-12 rounded scroll-smooth before:w-[45vw] before:shrink-0 after:w-[45vw] after:shrink-0 md:before:w-0 md:after:w-0" ref="slidesContainer">
            <div class="w-[200px] h-[300px] lg:h-[350px] xl:h-[400px] 2xl:h-[450px] grid  mx-auto md:w-[350px] lg:w-[325px] xl:w-[400px] 2xl:w-[490px] slide aspect-square  flex-shrink-0 snap-center overflow-hidden">
                <img @click="open" src="../../assets/images/portfolio/1.png" alt="" class="p-2 w-full h-[180px] lg:h-[250px] xl:h-[300px] 2xl:h-[350px]  object-cover">
                <div class="text-center font-jost text-[#E3E7F2]">
                    <p class="text-[14px] font-[600]">- 01 -</p>
                    <h2 class="text-[16px] font-[600]">{{$t('translation.cardclient.one')}}</h2>
                    <p class="text-[15px] font-[400] text-[#808288]"> {{$t('translation.cardclient.two')}}</p>
                </div>
            </div>
            <div class="w-[200px]  h-[300px] lg:h-[350px] xl:h-[400px] 2xl:h-[450px] grid  mx-auto md:w-[350px] lg:w-[325px] xl:w-[400px] 2xl:w-[490px] slide aspect-square  flex-shrink-0 snap-center overflow-hidden">
                <img  @click="open" src="../../assets/images/portfolio/2.png" alt="" class="p-2 w-full h-[180px] lg:h-[250px] xl:h-[300px]  2xl:h-[350px] object-cover">
                <div class="text-center font-jost text-[#E3E7F2]">
                    <p class="text-[14px] font-[600]">- 01 -</p>
                    <h2 class="text-[16px] font-[600]">{{$t('translation.cardclient.one')}}</h2>
                    <p class="text-[15px] font-[400] text-[#808288]"> {{$t('translation.cardclient.two')}}</p>
                </div>
            </div>
            <div class="w-[200px]  h-[300px] lg:h-[350px] xl:h-[400px] 2xl:h-[450px] grid  mx-auto md:w-[350px] lg:w-[325px] xl:w-[400px] 2xl:w-[490px] slide aspect-square  flex-shrink-0 snap-center overflow-hidden">
                <img  @click="open" src="../../assets/images/portfolio/3.png" alt="" class="p-2 w-full h-[180px] lg:h-[250px] xl:h-[300px]  2xl:h-[350px] object-cover">
                <div class="text-center font-jost text-[#E3E7F2]">
                    <p class="text-[14px] font-[600]">- 01 -</p>
                    <h2 class="text-[16px] font-[600]">{{$t('translation.cardclient.one')}}</h2>
                    <p class="text-[15px] font-[400] text-[#808288]"> {{$t('translation.cardclient.two')}}</p>
                </div>
            </div>
            <div class="w-[200px]  h-[300px] lg:h-[350px] xl:h-[400px] 2xl:h-[450px] grid  mx-auto md:w-[350px] lg:w-[325px] xl:w-[400px] 2xl:w-[490px] slide aspect-square  flex-shrink-0 snap-center overflow-hidden">
                <img  @click="open" src="../../assets/images/portfolio/1.png" alt="" class="p-2 w-full h-[180px] lg:h-[250px] xl:h-[300px]  2xl:h-[350px] object-cover">
                <div class="text-center font-jost text-[#E3E7F2]">
                    <p class="text-[14px] font-[600]">- 01 -</p>
                    <h2 class="text-[16px] font-[600]">{{$t('translation.cardclient.one')}}</h2>
                    <p class="text-[15px] font-[400] text-[#808288]"> {{$t('translation.cardclient.two')}}</p>
                </div>
            </div>
        </div>

       <div class="flex justify-center items-center gap-4 md:gap-0 mt-[32px] md:mt-[56px] xl:mt-[48px]">
        <div class="md:w-[10%] lg:w-[10%] xl:w-[8%] 2xl:w-[6%] flex items-center gap-[20px]">
            <div class=" top-0 -left-4 h-full items-center ">
                <button @click="prevSlide" role="button" class="prev p-[15px] text-[#E3E7F2] border border-[#E3E7F2] hover:bg-[#E3E7F2] hover:text-white group" aria-label="prev">
                    <i class='bx bx-left-arrow-alt text-[36px]'></i> 
                </button>
            </div>
            <div class=" top-0 -right-4 h-full items-center">
                <button @click="nextSlide" role="button" class="next p-[15px] text-[#E3E7F2] border border-[#E3E7F2] hover:bg-[#E3E7F2] hover:text-white group" aria-label="next">
                    <i class='bx bx-right-arrow-alt text-[36px]' ></i>
                </button>
            </div>
        </div>
       </div>
    </div>
    <ModalOneTwo @close="close" v-if="modal1"/>
</template>

<script setup>
    import { ref, computed, onMounted, onBeforeUnmount } from 'vue';
    import ModalOneTwo from '../Modal/ModalOneTwo.vue';

    const modal1 = ref(false);

    const open = () => {
        modal1.value = true;
    };
    
    const close = () => {
        modal1.value = false;
    };

    const slidesContainer = ref(null); // Ref to the slides container element

    const slideWidth = computed(() => {
    if (!slidesContainer.value) return 0;
    return slidesContainer.value.querySelector('.slide').clientWidth;
    });

    const scrollLeft = (amount) => {
    if (!slidesContainer.value) return;
    slidesContainer.value.scrollLeft += amount;
    };

    const nextSlide = () => scrollLeft(slideWidth.value);
    const prevSlide = () => scrollLeft(-slideWidth.value);

    const onSlideChange = (event) => {
    // Handle slide change event (optional)
    };

    onMounted(() => {
        slidesContainer.value.addEventListener('scroll', onSlideChange);
    });

    onBeforeUnmount(() => {
        slidesContainer.value.removeEventListener('scroll', onSlideChange);
    });
</script>


<style lang="scss" scoped>
    .slides-container {
        -ms-overflow-style: none; /* Internet Explorer 10+ */
        scrollbar-width: none; /* Firefox */
    }
    .slides-container::-webkit-scrollbar {
        display: none; /* Safari and Chrome */
    }

</style>