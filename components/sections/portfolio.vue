<template>
	<div class="portfolio">
		<section class="portfolio__inside">
			<h1 class="portfolio__title">Мои работы</h1>
			<WorkGrid class="portfolio__grid"/>
			<WorksSlider class="portfolio__slider"/>
			<buttonUI class="portfolio__btn">Больше работ в Instagram</buttonUI>
		</section>
	</div>
</template>

<script>
import WorkGrid from '~/components/general/workGrid';
import WorksSlider from '~/components/general/worksSlider';
import buttonUI from '~/components/ui/buttonUI';
export default {
	components: {
		WorkGrid,
		WorksSlider,
		buttonUI
	}
}
</script>

<style lang="scss" scoped>
.portfolio {
	&__inside {
		padding: 0 66px;
		display: flex;
		flex-direction: column;

		@media (max-width: $xxl) {
			padding: 36px;
		}

		@media (max-width: $md) {
			padding: 16px;
		}
	}

	&__title {
		@include h1;

		@media (max-width: $lg) {
			@include h1--tablet;
		}

		@media (max-width: $sm) {
			@include h2;
			text-align: center;
		}
	}

	&__grid {
		margin-top: 30px;

		@media (max-width: $md) {
			display: none;
		}
	}

	&__btn {
		margin: 36px auto 0 auto;
		padding: 21px 53px;

		@media (max-width: $lg) {
			padding: 8px 15px;
			margin: 64px auto 0 auto;
		}
	}

	&__slider {
		display: none;
		margin-top: 36px;
		
		@media (max-width: $md) {
			display: block;
			margin-top: 48px;
		}
	}
}
</style>