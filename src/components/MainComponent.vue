<script setup>
import FAQComponent from './FAQComponent.vue';
</script>
<template>
    <main class="main">
        <div class="running-line">
			<div class="running-line__first-half">
				<p>#АНАЛИЗИРУЙ СОСТОЯНИЕ РЫНКА</p>
				<p>#ОТСЛЕЖИВАЙ ДИНАМИКУ ЦЕН</p>
				<p>#ИССЛЕДУЙ ТРЕНДЫ</p>
			</div>
			<div class="running-line__second-half">
				<p>#ПРОГНОЗИРУЙ ПРИБЫЛЬ</p>
				<p>#НАХОДИ ЛУЧШИЕ ИНВЕСТИЦИИ</p>
				<p>#ПРИНИМАЙ РЕШЕНИЯ</p>
			</div>
		</div>
        <iframe class="iframe" title="cs2_market" src="https://app.powerbi.com/view?r=eyJrIjoiM2ZhNzVkNjgtMjFjNy00MWUxLWEzNmEtYjI5NzFlMzYxZjU3IiwidCI6ImI4MmQ2N2FmLWJmMGQtNGJjOS04Y2QxLWE0ZWQwZTBlMzVjOSIsImMiOjl9&pageName=ReportSection7eba521a22001b652321" frameborder="0" allowFullScreen="true" >
        </iframe>
        <FAQComponent></FAQComponent>
    </main>
</template>

<style lang="sass">
$duration: 20s

.main
    background-image: url("../assets/main_BG.png")
    background-position: center bottom
    background-size: cover
    background-color: #0b1d2a // Страховочный фон
    display: flex
    flex-direction: column
    align-items: center
    width: 100%
    min-height: 100%
    flex: 1 0 auto

    .iframe
        width: 70vw
        height: 90vh
        box-shadow: 0px 0px 60px rgba(0, 0, 0, 0.62)
        border-radius: 10px
        overflow: hidden
        display: block
        border: none

        @media screen and (max-width: 1720px)
            width: 90%
            height: 90vh

        @media screen and (max-width: 1500px)
            width: 74vw
            height: 82.5vh

        @media screen and (max-width: 1440px) // Упорядочил по убыванию
            width: 82vw
            height: 70vh

        @media screen and (max-width: 1400px)
            height: 84vh

        @media screen and (max-width: 1280px)
            height: 80vh

        @media screen and (max-width: 820px)
            width: 84vw
            height: 55vh

        @media screen and (max-width: 750px)
            width: 85vw
            height: 50vh

        @media screen and (max-width: 482px)
            width: 95vw
            height: 40vh

        @media screen and (max-width: 325px)
            width: 95vw
            height: 29vh

.running-line
    margin-top: 10px
    margin-bottom: 0
    padding-bottom: 20px
    min-height: 43px
    width: 100%
    position: relative

    &__first-half, &__second-half
        display: flex
        flex-direction: row
        justify-content: space-around
        align-items: center
        position: absolute
        overflow: hidden
        transform: translate(100%, 0)
        top: 0
        right: 0
        width: 100%
        height: 43px
        animation: ticker $duration infinite linear forwards

        p
            font-size: 2em
            text-transform: uppercase
            white-space: nowrap
            padding-bottom: 10px

            @media screen and (max-width: 1320px)
                font-size: 1.6em

            @media screen and (max-width: 1100px)
                font-size: 1.2em

            @media screen and (max-width: 800px)
                font-size: 1em

            @media screen and (max-width: 680px)
                font-size: 0.8em

            @media screen and (max-width: 560px)
                font-size: 0.6em

            @media screen and (max-width: 450px)
                font-size: 0.48em

            @media screen and (max-width: 330px)
                font-size: 0.44em

    &__second-half
        animation-delay: $duration / 2

    @keyframes ticker
        0%
            transform: translate(100%, 0)
        50%
            transform: translate(0, 0)
        100%
            transform: translate(-100%, 0)

</style>
