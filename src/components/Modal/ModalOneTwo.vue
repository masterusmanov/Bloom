<template>
    <div @click="open" class="w-full h-[180vh] bg-[#1E1E1E] bg-opacity-20 top-0 right-0 left-0 flex justify-center items-center fixed z-50 border-none outline-none font-jost">
        <div class="w-[90%] lg:w-[35%] 2xl:w-[30%] p-[24px] bg-black self-start mt-[30%] lg:mt-[10%] max-w-screen-md max-h-screen-xl">
            <div class="flex justify-between  items-center h-[60px]">
                <div class="w-[85%] flex items-center gap-2 md:w-[40%]">
                    <h2 class="text-[#E3E7F2] text-[24px] font-[600] font-jost">{{ $t('translation.modalTwo.one') }}</h2>
                 </div>
                <div @click="emitClose" class="ml-[25px]">
                    <i class='bx bx-x text-[#E3E7F2] text-[36px]'></i>
                </div>
            </div> 
            <div class="mt-[20px] grid xl:flex gap-[10px] text-[#E3E7F2]">
                <div class="xl:w-1/2 grid gap-2">
                    <img src="../../assets/images/portfolio/2.png" alt="" class="xl:w-[200px] ">
                    <p class="font-jost">{{ $t('translation.modalTwo.two') }}</p>
                    <img src="../../assets/images/portfolio/render.svg" alt="" class="lg: w-[400px] xl:w-[200px] lg:h-[60px]">
                </div>
                <div class="hidden xl:block xl:w-1/2">
                    <h1 class="font-jost">{{ $t('translation.modalTwo.three') }}</h1>
                    <p class="font-jost text-justify">{{ $t('translation.modalTwo.four') }}</p>
                    
                    <h1 class="font-jost mt-[20px]">{{ $t('translation.modalTwo.five') }}</h1>
                    <p class="font-jost">{{ $t('translation.modalTwo.six') }}</p>
                    
                    <h1 class="font-jost mt-[20px]">{{ $t('translation.modalTwo.seven') }}</h1>
                    <p class="font-jost">2000 x 10000 m2</p>

                    <h1 class="font-jost mt-[20px]">{{ $t('translation.modalTwo.eight') }}</h1>
                    <p class="font-jost">Uzbekistan, Tashkent, Navoiy 45</p>

                    <h1 class="font-jost mt-[20px]">{{ $t('translation.modalTwo.nine') }}</h1>
                    <p class="font-jost">ООО “Genius Group”</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
    import { ref } from 'vue'
    import axios from 'axios'
    import { defineEmits } from 'vue';

    const emit = defineEmits(['close']);
    function emitClose() {
    emit('close');
    }

    const phone_number = ref('');
    const name = ref('');
    const response = ref(null);
    const error = ref(null);

    const submitForm = async () => {
        try {
            const requestBody = {
                phone_number: phone_number.value,
                name: name.value,
            };
            
            const token = localStorage.getItem('token');

            const apiResponse = await axios.post('https://bloom-backend-6ddzy.ondigitalocean.app/admin/order', requestBody, {
                headers: {
                    Authorization: `Bearer ${token}`,
                    'Content-Type': 'application/json',
                }
            });

            if (apiResponse.status === 201) {
               alert('Success!');
            }else{
                alert('Error')
            }

            response.value = apiResponse.data;
            error.value = null;
        } catch (e) {
            response.value = null;
            error.value = e.message;
        }
    };

</script>

<style lang="scss" scoped>
</style>