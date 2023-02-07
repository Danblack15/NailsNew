<template>
	<div class="price">
		<section class="price__inside">
			<BigTitle value="price" />

			<PriceGrid class="price__grid"/>
		</section>
	</div>
</template>

<script>
import BigTitle from '@/components/ui/bigTitle'
import PriceGrid from '@/components/general/priceGrid'
export default {
	components: {
		BigTitle,
		PriceGrid
	}
}
</script>

<style lang="scss" scoped>
.price {
	&__inside {
		padding: 0 66px;

		@media (max-width: $xxl) {
			padding: 0 36px;
		}

		@media (max-width: $md) {
			padding: 0 16px;
		}
	}

	&__grid {
		margin-top: 36px;
	}
}
</style>