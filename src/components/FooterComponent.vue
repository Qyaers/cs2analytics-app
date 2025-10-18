<script setup>
import { ref } from 'vue';
const currentYear = ref(new Date().getFullYear());
</script>



<template>
    <footer class="footer">
        <div class="footer__text"><p>Galaxy Studios</p></div>
        <div class="footer__text"><p>© {{ currentYear }}</p></div>
    </footer>
</template>

<style>
.footer{
    width: 100%;
    height: 100%;
    height: 10vh;
    background-color: #063159;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    padding: 20px;
}

</style>
