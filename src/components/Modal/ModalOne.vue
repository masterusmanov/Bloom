<template>
    <div @click="open" class="w-full h-[180vh] bg-[#1E1E1E] bg-opacity-20 top-0 right-0 left-0 flex justify-center items-center fixed z-50 border-none outline-none font-jost">
        <div class="w-[90%] lg:w-[35%] 2xl:w-[30%] p-[24px] bg-black self-start mt-[50%] lg:mt-[15%] max-w-screen-md max-h-screen-xl">
            <div class="flex justify-between  items-center h-[60px]">
                <div class="w-[85%] flex items-center gap-2 md:w-[40%]">
                    <h2 class="text-[#E3E7F2] text-[24px] font-[600] font-jost">{{ $t('translation.modalOne.one') }}</h2>
                 </div>
                <div @click="emitClose" class="ml-[25px]">
                    <i class='bx bx-x text-[#E3E7F2] text-[36px]'></i>
                </div>
            </div> 
            <form >
                <div class="grid gap-[20px] mt-[26px]">
                    <input type="text" v-model="name" id="name" :placeholder="$t('translation.modalOne.two')" class="outline-none bg-black border-b text-[#E3E7F2] border-[#E3E7F2]">
                    <input type="tel" v-model="phone_number" id="phone_number" :placeholder="$t('translation.modalOne.three')" class="outline-none bg-black border-b text-[#E3E7F2] border-[#E3E7F2]">
                </div>
                <div class="flex items-center justify-between mt-[34px]">
                    <p class="text-[#94979D] text-[16px] font-[400] font-jost lg:w-[50%]">{{ $t('translation.modalOne.four') }}</p>
                    <button type="submit" @onclick="submitForm" class="bg-black border border-[#E3E7F2] w-[120px] h-[120px] p-4 cursor-pointer">
                        <svg class="ml-[60px]" xmlns="http://www.w3.org/2000/svg" width="34" height="34" viewBox="0 0 34 34" fill="none">
                            <path d="M25.189 11.7936C25.2556 13.8304 26.264 15.3555 27.2012 16.1485L27.9047 15.317C27.1731 14.6979 26.333 13.4502 26.2777 11.758C26.2228 10.0811 26.7143 8.09914 29.2559 5.55751L28.4857 4.7873C25.944 7.32896 23.9621 7.82035 22.2852 7.76552C20.5929 7.71017 19.3453 6.87009 18.7262 6.13844L17.8947 6.84202C18.6877 7.77915 20.2128 8.78756 22.2496 8.85417C23.0473 8.88026 23.9097 8.76164 24.8244 8.44857L4.8318 28.4412L5.602 29.2114L25.5946 9.21878C25.2815 10.1334 25.1629 10.9959 25.189 11.7936Z" fill="#E3E7F2"/>
                        </svg>
                        <div class="grid gap-3 lg:gap-0 mt-[16px] lg:mt-[32px]">
                            <p class="text-[#E3E7F2] text-[14px] lg:text-[16px] font-jost proportional-nums leading-[14px] lg:w-[50%]">{{$t('translation.modal.one')}}</p>
                            <p class="text-[#E3E7F2] text-[14px] lg:text-[16px] font-jost proportional-nums leading-[14px] lg:w-[50%]">{{$t('translation.modal.two')}}</p>
                          </div>
                    </button>
                </div>
            </form>
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