<template>
    <div class="container mx-auto relative mt-[120px] lg:mt-[250px] 2xl:mt-[350px]">

        <div class="flex justify-end p-4 items-center gap-4 md:gap-0 my-[32px] md:my-[56px] xl:my-[48px] xl:mr-[60px] 2xl:mr-[60px]">
            <div class="md:w-[10%] lg:w-[10%] xl:w-[8%] 2xl:w-[6%] flex items-center gap-[20px]">
                <div class=" top-0 -left-4 h-full items-center ">
                    <button @click="prevSlide" role="button" class="prev p-[15px] text-[#E3E7F2] border border-[#E3E7F2] hover:bg-[#E3E7F2] hover:text-black group hover:rounded-b-full hover:rounded-tr-full" aria-label="prev">
                        <i class='bx bx-left-arrow-alt text-[36px]'></i> 
                    </button>
                </div>
                <div class=" top-0 -right-4 h-full items-center">
                    <button @click="nextSlide" role="button" class="next p-[15px] text-[#E3E7F2] border border-[#E3E7F2] hover:bg-[#E3E7F2] hover:text-black group hover:rounded-b-full hover:rounded-tl-full" aria-label="next">
                        <i class='bx bx-right-arrow-alt text-[36px]' ></i>
                    </button>
                </div>
            </div>
           </div>

        <div class="slides-container  flex snap-x snap-mandatory overflow-hidden overflow-x-auto space-x-12 rounded scroll-smooth before:w-[45vw] before:shrink-0 after:w-[45vw] after:shrink-0 md:before:w-0 md:after:w-0" ref="slidesContainer">
            <div class=" bg-[#E3E7F2] w-[250px] h-[150px] lg:w-[300px] lg:h-[200px] xl:w-[350px] xl:h-[250px] grid  mx-auto slide aspect-square p-4  flex-shrink-0 snap-center overflow-hidden">
                <img src="../../assets/images/logos/1.svg" alt="" class=" w-[100%]">
                <div class="text-center font-jost mt-[30px]">
                    <p class="text-[15px] font-[400] text-[#808288]"> {{$t('translation.cardclientTwo')}}</p>
                </div>
            </div>
            <div class=" bg-[#E3E7F2] w-[250px] h-[150px] lg:w-[300px] lg:h-[200px] xl:w-[350px] xl:h-[250px] grid  mx-auto slide aspect-square p-4  flex-shrink-0 snap-center overflow-hidden">
                <img src="../../assets/images/logos/2.svg" alt="" class=" w-[100%]">
                <div class="text-center font-jost mt-[30px]">
                    <p class="text-[15px] font-[400] text-[#808288]"> {{$t('translation.cardclientTwo')}}</p>
                </div>
            </div>
            <div class=" bg-[#E3E7F2] w-[250px] h-[150px] lg:w-[300px] lg:h-[200px] xl:w-[350px] xl:h-[250px] grid  mx-auto slide aspect-square p-4  flex-shrink-0 snap-center overflow-hidden">
                <img src="../../assets/images/logos/3.svg" alt="" class=" w-[100%]">
                <div class="text-center font-jost mt-[30px]">
                    <p class="text-[15px] font-[400] text-[#808288]"> {{$t('translation.cardclientTwo')}}</p>
                </div>
            </div>
            <div class=" bg-[#E3E7F2] w-[250px] h-[150px] lg:w-[300px] lg:h-[200px] xl:w-[350px] xl:h-[250px] grid  mx-auto slide aspect-square p-4  flex-shrink-0 snap-center overflow-hidden">
                <img src="../../assets/images/logos/1.svg" alt="" class=" w-[100%]">
                <div class="text-center font-jost mt-[30px]">
                    <p class="text-[15px] font-[400] text-[#808288]"> {{$t('translation.cardclientTwo')}}</p>
                </div>
            </div>
            <div class=" bg-[#E3E7F2] w-[250px] h-[150px] lg:w-[300px] lg:h-[200px] xl:w-[350px] xl:h-[250px] grid  mx-auto slide aspect-square p-4  flex-shrink-0 snap-center overflow-hidden">
                <img src="../../assets/images/logos/2.svg" alt="" class=" w-[100%]">
                <div class="text-center font-jost mt-[30px]">
                    <p class="text-[15px] font-[400] text-[#808288]"> {{$t('translation.cardclientTwo')}}</p>
                </div>
            </div>
            
        </div>

       
    </div>
</template>

<script setup>
    import { ref, computed, onMounted, onBeforeUnmount } from 'vue';

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