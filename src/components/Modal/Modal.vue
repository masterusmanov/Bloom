<template>
    <div class="hover:text-center">
        <div class="float-right w-[50%] ml-[50px] lg:hidden">
          <svg xmlns="http://www.w3.org/2000/svg" width="34" height="34" viewBox="0 0 34 34" fill="none">
            <path d="M25.189 11.7936C25.2556 13.8304 26.264 15.3555 27.2012 16.1485L27.9047 15.317C27.1731 14.6979 26.333 13.4502 26.2777 11.758C26.2228 10.0811 26.7143 8.09914 29.2559 5.55751L28.4857 4.7873C25.944 7.32896 23.9621 7.82035 22.2852 7.76552C20.5929 7.71017 19.3453 6.87009 18.7262 6.13844L17.8947 6.84202C18.6877 7.77915 20.2128 8.78756 22.2496 8.85417C23.0473 8.88026 23.9097 8.76164 24.8244 8.44857L4.8318 28.4412L5.602 29.2114L25.5946 9.21878C25.2815 10.1334 25.1629 10.9959 25.189 11.7936Z" fill="#E3E7F2"/>
          </svg>
        </div>
        <div class="float-right ml-[100px] xl:ml-[130px] hidden lg:block">
          <svg xmlns="http://www.w3.org/2000/svg" width="80" height="90" viewBox="0 0 90 90" fill="none">
            <path d="M66.6789 31.2201C66.8552 36.6117 69.5245 40.6488 72.0052 42.7478L73.8676 40.5467C71.9309 38.9079 69.7071 35.6054 69.5606 31.1259C69.4155 26.6871 70.7163 21.4407 77.4441 14.7129L75.4053 12.6741C68.6774 19.402 63.4312 20.7028 58.9924 20.5576C54.5129 20.4111 51.2103 18.1874 49.5715 16.2506L47.3705 18.1131C49.4695 20.5937 53.5065 23.263 58.8981 23.4393C61.0096 23.5084 63.2926 23.1944 65.7138 22.3657L12.7922 75.2873L14.831 77.3261L67.7525 24.4045C66.9238 26.8257 66.6098 29.1086 66.6789 31.2201Z" fill="#E3E7F2"/>
          </svg>
        </div>
        <div class="grid gap-1 lg:gap-0 mt-[16px]">
          <p class="text-[#E3E7F2] text-[14px] lg:text-[30px] font-jost proportional-nums leading-[14px] lg:w-[100%]">{{$t('translation.modal.one')}}</p>
          <p class="text-[#E3E7F2] text-[14px] lg:text-[30px] font-jost proportional-nums leading-[14px] lg:w-[100%]">{{$t('translation.modal.two')}}</p>
        </div>
      </div>
</template>

<script setup>
    import { defineEmits } from 'vue';

    const emit = defineEmits(['close']);
    function emitClose() {
    emit('close');
    }
</script>

<style lang="scss" scoped>

</style>