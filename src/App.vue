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
html
  width: 100%
  height: 100%
body
  overflow-x: hidden
  height: 100%
  min-height: 100%
  width: 100%
  height: -webkit-fill-available
  height: fill-available

  overflow-y: auto
  overflow-x: hidden
  
  scroll-behavior: smooth
  
  overscroll-behavior: contain
  
  -webkit-overflow-scrolling: auto
  touch-action: pan-y
p,h1,h2,a
  font-family: Roboto, sans-serif
  font-weight: bold
p
  color: #ffffff
</style>
