<script setup>
import HeaderComponent from "./components/HeaderComponent.vue"
import MainComponent from "./components/MainComponent.vue"
import FooterComponent from "./components/FooterComponent.vue"


</script>

<template>
  <HeaderComponent></HeaderComponent>
  <MainComponent></MainComponent>
  <FooterComponent></FooterComponent>
</template>

<style lang="sass">
* 
  padding: 0
  margin: 0
  box-sizing: border-box
  user-select: none
  font-family: Roboto sans-serif
  font-weight: bold
  color: #fff

body
  width: 100vw
  height: 100vh
  overflow-x: hidden

p,h1,h2
  font-family: Roboto, sans-serif
  font-weight: bold
p
  color: #ffffff
</style>
