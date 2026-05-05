<script setup>
import { computed } from 'vue';
const currentYear = new Date().getFullYear();
const yearText = computed(()=> currentYear == "2025"? "2025": `2025 - ${currentYear}`); 

</script>



<template>
    <footer class="footer">
        <div class="footer__text"><p>Galaxy Studios</p></div>
        <div class="footer__text"><p>© {{ yearText }}</p></div>
    </footer>
</template>

<style lang="sass">
.footer
    width: 100%
    min-height: 10vh
    background-color: #063159
    display: flex
    flex-direction: column
    justify-content: space-around
    padding: 20px
    position: relative
</style>
