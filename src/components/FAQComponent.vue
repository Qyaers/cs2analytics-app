<template>
	<div id="faq" class="faq__container container">
    <div class="faq__about-project">
        <h2 class="about-project__title">Проект</h2>
        <p class="about-project__text">Аналитический дашборд для изучения рынка предметов Counter Strike 2</p>
    </div>
	<h2>FAQ</h2>
		<div class="faq" v-for="(faqItem, index) in faqItems" :key="index" :faq="faqItem">
            <div class="question" @click="toggleAnswer(index,faqItem)">
                <p class="question-text">{{ faqItem.q }}</p>
                <p class="toggle-icon">
                    {{faqItem.isOpen ? "—" : "＋" }}
                </p>
            </div>
            <div class="answer" ref="answer">
                <p>{{ faqItem.a}}</p>
                <ul v-if="faqItem.hasOwnProperty('list')" v-for="item in faqItem.list">
                    <li>
                    {{item}}
                    </li>
                </ul>
            </div>
		</div>
	</div>
</template>
<script>
export default {
	data() {
		return {
			faqItems: [
				{
					q: `Из чего состоит дашборд?`,
					a:
						`Дашборд включает в себя статистику по всем предметам в Counter Strike 2.`,
					isOpen: false
				},
				{
					q: `Чем полезен дашборд?`,
					a:
						`Дашборд предоставляет возможности для принятия инвестиционных решений на основе анализа динамики цен на предметы.`
					,
				},
				{
					q: `Как пользоваться дашбордом?`,
					a:
						`Изучайте историю цен на отдельные предметы или группы предметов в различных разрезах. Сравнивайте предметы по прибыли и росту или снижению цен за последние 7, 30 или 365 дней.`
				},
				{
					q: `Что означают эти графики и показатели?`,
					a:
						`История продаж: динамика средней цены в руб. на предмет в разрезе дней, месяцев, кварталов и лет.Топ-100 предметов по прибыли: топ самых прибыльных предметов по формулам “Макс цена продажи за период” / “Мин цена продажи за период” и “Макс цена продажи за период” / “Средняя цена продажи за период”.Топ-100 предметов по росту/снижению цены: топ предметов по росту/снижению цены за последние 7/30/365 дней.`
				},
				{
					q: `Откуда берутся данные?`,
					a: `Все данные взяты напрямую с торговой площадки Steam. Парсер доступен в репозитории (https://github.com/PushinIlya/CS2-Analytics).`
				}
			],
		};
	},
	methods: {
		toggleAnswer(index, faqItem) {
			if (faqItem.isOpen) {
				this.collapse(index);
			} else {
				this.expand(index);
			}
			faqItem.isOpen = !faqItem.isOpen
		},
		collapse(index) {
			const answer = this.$refs.answer[index];
			answer.style.height = 0;
		},
		expand(index) {
			const answer = this.$refs.answer[index];
			answer.style.height = answer.scrollHeight + "px";
		}
	}
}
</script>
<style lang="sass">
.faq__container
    display: flex
    flex-direction: column
    flex-shrink: 0
    flex-wrap: wrap
    width: 80%
    padding-bottom: 4vh
    padding-top: 4vh
.faq
    display: flex
    flex-direction: column
    justify-content: space-between
    width: 100%
    &__about-project
        margin: 20px 0px 20px 0px
.about-project
    &__title
        padding-bottom:10px

.question
    display: flex
    flex-direction: row
    justify-content: space-between
    margin-top: 20px
    background: #06315980
    padding: 10px 0
    transition: transform 0.2s
    position: relative
    padding-left: 0.8vw
    cursor: pointer
    border-top-left-radius: 15px
    border-top-right-radius: 15px
    .question-text
        font-size: 1.5em
        font-weight: bold
        @media screen and (max-width: 1680px)
            font-size: 1.25em
            padding: 10px	
        @media screen and (max-width: 1200px)
            font-size: 1em
            padding: 10px	
        @media screen and (max-width: 1000px)
            font-size: 0.85em
            padding: 10px	
        @media screen and (max-width: 800px)
            font-size: 0.825em
            padding: 10px	
.question:hover
    background: rgba(27, 128, 176, 0.2)

.question:active
    transform: translateY(4px)
    box-shadow: none

.question:has(+ .answer[style*="height: 0px"]),
.question:has(+ .answer[style*="height: 0"])
    border-radius: 15px


.question:has(+ .answer:not([style*="height: 0"]))
    border-bottom-left-radius: 0
    border-bottom-right-radius: 0

.answer 
    transition: 0.25s
    height: 0
    overflow: hidden
    text-align: justify
    background: #06315980
    border-bottom-right-radius: 15px
    border-bottom-left-radius: 15px
    p,ul,li,span
        margin: 0
        list-style-type: disc
    p
        font-size: 1.25em
        padding: 5px 20px 5px 20px
        @media screen and (max-width: 1680px)
            font-size: 1.15em
        @media screen and (max-width: 1200px)
            font-size: 1em
            padding-right: 20px
        @media screen and (max-width: 800px)
            font-size: 1em
            padding-right: 20px
    li
        font-size: 1.25em
        @media screen and (max-width: 1680px)
            font-size: 1.15em
        @media screen and (max-width: 1200px)
            font-size: 1em
            padding-right: 20px
        @media screen and (max-width: 800px)
            font-size: 1em
            padding-right: 20px
h2
    font-size: 2em
.toggle-icon
    font-size: 1em
    font-weight: bold
    display: inline-block
    line-height: 0.5
    color: #666
    margin-top: 15px
    padding-right: 20px
</style>