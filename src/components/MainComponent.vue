<script setup>
</script>
<template>
    <main class="main">
        <div class="running-line ticker-wrapper">
			<div class="ticker-wrapper__first-half">
				<p>#исследуй тренды</p>
				<p>#анализируй рынок</p>
				<p>#принимай лучшее решение</p>
			</div>
			<div class="ticker-wrapper__second-half">
				<p>#прогнозируй рост</p>
				<p>#изучай цены</p>
				<p>#находи аномалии</p>
			</div>
		</div>
        <iframe class="iframe" title="cs2_market" src="https://app.powerbi.com/view?r=eyJrIjoiM2ZhNzVkNjgtMjFjNy00MWUxLWEzNmEtYjI5NzFlMzYxZjU3IiwidCI6ImI4MmQ2N2FmLWJmMGQtNGJjOS04Y2QxLWE0ZWQwZTBlMzVjOSIsImMiOjl9&pageName=ReportSection7eba521a22001b652321" frameborder="0" allowFullScreen="true" >
        </iframe>
    </main>
</template>

<style lang="sass">
.main
    background-image: url("../assets/main_BG.png")
    background-size: cover
    display: flex
    flex-direction: column
    align-items: center
    width: 100vw
    height: 100%
    padding-top: 10px
    padding-bottom: 10px
    iframe
        width: 70vw
        height: 90vh
        box-shadow: 0px 0px 60px #0000009f
        border-radius: 10px
        overflow: hidden
        @media screen and (max-width: 1720px)
            width: 90%
            height: 90vh
        @media screen and (max-width: 1500px)
            width: 74vw
            height: 82.5vh

        @media screen and (max-width: 1400px)
            width: 82vw
            height: 84vh
        @media screen and (max-width: 1440px)
            width: 82vw
            height: 70vh
        @media screen and (max-width: 1320px)
            width: 82vw
        @media screen and (max-width: 1280px)
            width: 82vw
            height: 80vh
        @media screen and (max-width: 820px)
            width: 84vw
            height: 55vh
.running-line 
    height: 5vh
    width: 100%
    position: relative
    overflow: hidden
    div.ticker-wrapper__first-half,.ticker-wrapper__second-half 
        display: flex
        flex-direction: row
        align-items: center
        overflow: hidden
        width: 100%
        height: 43px
        transform: translate(100%, 0)
        p 
            font-size: 2em
            text-transform: uppercase
            @media screen and (max-width: 1320px)
                font-size: 1.6em
                padding-bottom: 20px

            @media screen and (max-width: 1100px)
                font-size: 1.2em
                padding-bottom: 20px

            @media screen and (max-width: 800px)
                font-size: 1em
                padding-bottom: 20px
    $duration: 20s
    .ticker-wrapper__first-half, .ticker-wrapper__second-half 
        display: flex
        flex-direction: row
        justify-content: space-around
        align-items: center
        position: absolute
        top: 0
        right: 0
        animation: ticker $duration infinite linear forwards
    .ticker-wrapper__second-half
        animation: $duration ticker $duration/2 infinite linear forwards
    @keyframes ticker 
        0% 
            transform: translate(100%, 0)
        50% 
            transform: translate(0, 0)
        100% 
            transform: translate(-100%, 0)
</style>
