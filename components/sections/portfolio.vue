<template>
	<div class="portfolio">
		<section class="portfolio__inside">
			<h1 class="portfolio__title">Мои работы</h1>
			<workGrid class="portfolio__grid"/>
			<buttonUI class="portfolio__btn">Больше работ в Instagram</buttonUI>
		</section>
	</div>
</template>

<script>
import workGrid from '~/components/general/workGrid';
import buttonUI from '~/components/ui/buttonUI';
export default {
	components: {
		workGrid,
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
	}

	&__title {
		@include h1;
	}

	&__grid {
		margin-top: 30px;
	}

	&__btn {
		margin: 36px auto 0 auto;
		padding: 21px 53px;
	}
}
</style>