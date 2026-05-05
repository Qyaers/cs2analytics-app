<script setup>
import { ref } from 'vue';


const akSkinLink = ref("/assets/ak_1.png")
const m4SkinLink = ref("/assets/m4a1s_1.png")
const awpSkinLink = ref("/assets/awp_1.png")
const counterAk = ref(0);
const counterM4 = ref(0);
const counterAWP = ref(0);

const akSkinsArray = [
    "/assets/ak_1.png",
    "/assets/ak_2.png",
    "/assets/ak_3.png",
    "/assets/ak_4.png",
    "/assets/ak_5.png"
];
const m4SkinsArray = [
    "/assets/m4a1s_1.png",
    "/assets/m4a1s_2.png",
    "/assets/m4a1s_3.png",
    "/assets/m4a1s_4.png",
    "/assets/m4a1s_5.png",
];
const awpSkinsArray = [
    "/assets/awp_1.png",
    "/assets/awp_2.png",
    "/assets/awp_3.png",
    "/assets/awp_4.png",
    "/assets/awp_5.png",
];

setInterval(changeAKSkin,2520,counterAk,akSkinsArray);
setInterval(changeAWPSkin,4220,counterAWP,awpSkinsArray);
setInterval(changeM4Skin,3520,counterM4,m4SkinsArray);

function changeM4Skin(counter,m4SkinsArray){
    counter.value++;
    if(counter.value == 5){
        counter.value = 0
        m4SkinLink.value = m4SkinsArray[counter.value]
    }
    m4SkinLink.value = m4SkinsArray[counter.value]
}

function changeAWPSkin(counter,awpSkinsArray){
    counter.value++;
    if(counter.value == 5){
        counter.value = 0
        awpSkinLink.value = awpSkinsArray[counter.value]
    }
    awpSkinLink.value = awpSkinsArray[counter.value]
}

function changeAKSkin(counter){
    counter.value++;
    if(counter.value == 5){
        counter.value = 0
        akSkinLink.value = akSkinsArray[counter.value]
    }
    akSkinLink.value = akSkinsArray[counter.value]
}

</script>

<template>
    <header class="header">
        <h1 class="header__title">Аналитика рынка CS2</h1>
        <div class="header__gallery">
            <div class="header__item">
                <transition name="changeGun"><img :key="akSkinLink" class="header__image" :src="akSkinLink"  alt="ak-skin"></transition>
            </div>
            <div class="header__item">
                <transition name="changeGun"><img :key="awpSkinLink" class="header__image" :src="awpSkinLink" alt="awp-skin"></transition>
            </div>
            <div class="header__item">
                <transition name="changeGun"><img :key="m4SkinLink" class="header__image" :src="m4SkinLink" alt="m4a1s-skin"></transition>
            </div>
        </div>
    </header>
</template>

<style lang="sass">
.header
    background-image: url("/assets/headerBG.webp")
    background-size: 100% 100%
    background-repeat: no-repeat
    height: 100%
    width: 100%
    display: flex
    flex-direction: column
    align-items: center
    justify-content: center
    position: relative
    overflow: hidden

    @media screen and (max-width: 1240px)
        height: 50vh

    &__title
        position: absolute
        margin-bottom: 20vh
        z-index: 2
        word-break: break-all
        color: #9AD6FB
        font-family: Roboto, sans-serif
        font-weight: bold
        text-shadow: 20px 5px 11px rgba(0, 0, 0, 0.589)
        font-size: 9em
        text-align: center

        @media screen and (max-width: 1600px)
            font-size: 5.5em

        @media screen and (max-width: 1100px)
            margin-bottom: 0
            font-size: 4.5em

        @media screen and (max-width: 880px)
            font-size: 3.5em

        @media screen and (max-width: 800px)
            font-size: 3.5em // Твоё значение из кода

        @media screen and (max-width: 720px)
            font-size: 2.5em

        @media screen and (max-width: 450px)
            font-size: 1.8em

        @media screen and (max-width: 400px)
            font-size: 1.6em

    &__gallery
        min-width: 100vw
        height: 100%
        display: flex
        justify-content: space-evenly
        align-items: center
        z-index: 3
        margin-top: 20%

        @media screen and (max-width: 1600px)
            margin-top: 24vh

    &__item
        height: 70vh
        width: 30vw
        display: flex
        justify-content: center
        align-items: center

        @media screen and (max-width: 1600px)
            height: 50vh
            width: 30vw

    &__image
        width: 100%
        height: 100%
        object-fit: contain
        padding: 0
        margin: 0

.changeGun-enter-active
    transition: all 1s ease
    opacity: 0
    position: absolute

.changeGun-leave-active
    transition: all 0.2s ease

.changeGun-enter-from
    transition: all 0.2s ease
    transform: translateX(-20px)
    opacity: 0

.changeGun-leave-to
    transform: translateX(20px)
    opacity: 0
</style>
