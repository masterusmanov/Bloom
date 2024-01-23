<template>
    <header class="mt-[5px] lg:mt-[50px]">
        <div class="container mx-auto flex justify-between lg:justify-start lg:gap-[23px] items-center lg:items-start p-[16px] lg:p-0 font-jost">
            <div>
                <img src="../../assets/images/Logo.png" alt="" class="w-[25px] lg:w-[43px]">
            </div>
            <div id="menu" class="w-[10%] float-right md:hidden">
                <div @click="open">
                    <p><i class='bx bx-menu text-[#E3E7F2] text-[36px]'></i></p>
                </div>
                <Menu @close="close" v-if="modal1"/>            
            </div>
        </div>
    </header>
</template>

<script setup>
    import '../../assets/main.css';
    import Menu from './Menu.vue';
    import { ref, onMounted } from "vue";
    import { useRouter } from "vue-router";
    import { useI18n } from 'vue-i18n';
    
    const {t} = useI18n({useScope: 'global'});

    function changeLanguage(event) {
        const selectedLanguage = event.target.value;
        console.log(selectedLanguage);
        localStorage.setItem("lang", selectedLanguage)
        window.location.reload()
    }

    const modal1 = ref(false);

    const open = () => {
        modal1.value = true;
    };
    
    const close = () => {
        modal1.value = false;
    };
</script>

<style lang="scss" scoped>

</style>