<template>
    <footer id="contact" class="mt-[156px] lg:mt-[190px] bg-black">
        <div class="container lg:ml-[30%] lg:w-[70%]">
            <div class="flex justify-between lg:justify-start lg:gap-[100px]">
                <div class="p-4">
                    <img src="../../assets/images/Logo.png" alt="Logo" class="w-[26px]">
                    <div class="grid text-[16px] gap-2 my-[30px] lg:text-[24px]">
                        <a href="#about" class="text-[#808288] hover:text-[#E3E7F2]">{{$t('translation.navbar.one')}}</a>
                        <a href="#services" class="text-[#808288] hover:text-[#E3E7F2]">{{$t('translation.navbar.two')}}</a>
                        <a href="#portfolio" class="text-[#808288] hover:text-[#E3E7F2]">{{$t('translation.navbar.three')}}</a>
                        <a href="#client" class="text-[#808288] hover:text-[#E3E7F2]">{{$t('translation.navbar.four')}}</a>
                        <a href="#contact" class="text-[#808288] hover:text-[#E3E7F2]">{{$t('translation.navbar.five')}}</a>
                    </div>
                </div>
                <div class="mt-[115px] text-right lg:hidden ">
                    <p class="w-[92%] mx-4 font-[500] py-[10px] px-[20px] font-jost text-[#E3E7F2] text-[14px]">+998 (90) 985 64 89</p>
                    <p class="w-[92%] mx-4 font-[500] py-[10px] px-[20px] font-jost text-[#E3E7F2] text-[14px]">{{$t('translation.footer.one')}}</p>
                    <p class="w-[92%] mx-4 font-[500] py-[10px] px-[20px] font-jost text-[#E3E7F2] text-[14px]">info@bloom-arc@gmail.com</p>
                </div>
                <div class="my-[18px] text-[#808288] hidden lg:flex items-center justify-start px-4 gap-[30px] text-[26px] mt-[250px]">
                    <a href="#"><i class='bx bxl-instagram border p-[14px] hover:bg-black hover:text-[#E3E7F2] group hover:rounded-b-full hover:rounded-tl-full' ></i></a>
                    <a href="#"><i class='bx bxl-behance border p-[14px] hover:bg-black hover:text-[#E3E7F2] group hover:rounded-b-full hover:rounded-tl-full'></i></a>
                    <a href="#"><i class='bx bxl-facebook border p-[14px] hover:bg-black hover:text-[#E3E7F2] group hover:rounded-b-full hover:rounded-tl-full'></i></a>
                    <a href="#"><i class='bx bxl-vk border p-[14px] hover:bg-black hover:text-[#E3E7F2] group hover:rounded-b-full hover:rounded-tl-full'></i></a>
                </div>
            </div>
            <div class="my-[18px] text-[#808288] flex items-center justify-start px-4 gap-[20px] text-[26px] lg:hidden group hover:rounded-b-full">
                <a href="#"><i class='bx bxl-instagram border p-[14px] hover:bg-black hover:text-[#E3E7F2] group hover:rounded-b-full hover:rounded-tl-full' ></i></a>
                <a href="#"><i class='bx bxl-behance border p-[14px] hover:bg-black hover:text-[#E3E7F2] group hover:rounded-b-full hover:rounded-tl-full'></i></a>
                <a href="#"><i class='bx bxl-facebook border p-[14px] hover:bg-black hover:text-[#E3E7F2] group hover:rounded-b-full hover:rounded-tl-full'></i></a>
                <a href="#"><i class='bx bxl-vk border p-[14px] hover:bg-black hover:text-[#E3E7F2] group hover:rounded-b-full hover:rounded-tl-full'></i></a>
            </div>
            <div class="mt-[60px] hidden lg:flex justify-between ">
                <p class="w-[92%] font-[500] py-[10px] font-jost text-[#E3E7F2] text-[20px]">+998 (90) 985 64 89</p>
                <p class="w-[92%] font-[500] py-[10px] font-jost text-[#E3E7F2] text-[20px]">{{$t('translation.footer.one')}}</p>
                <p class="w-[92%] font-[500] py-[10px] font-jost text-[#E3E7F2] text-[20px]">info@bloom-arc@gmail.com</p>
            </div>
            <div class="mt-[40px] border-t border-[#E3E7F2]">
                <p class="w-[92%] mx-4 font-[500] py-[10px] font-jost text-[#E3E7F2] text-[14px] text-center lg:text-left">© {{new Date().getFullYear()}}. {{$t('translation.footer.two')}}</p>
            </div>
        </div>
    </footer>
</template>

<script setup>

</script>

<style lang="scss" scoped>

</style>