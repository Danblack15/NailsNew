<template>
	<div class="price-grid">
		<div 
			v-for="service in price"
			:key="service.id"
			class="price-grid__item"
		>
			<p class="price-grid__title">{{ service.title }}</p>
			<div class="price-grid__dashed"></div>
			<p class="price-grid__cost">{{ service.price }} р.</p>
		</div>
	</div>
</template>

<script>
import PriceData from '@/data/enums/price'

export default {
	data() {
		return {
			price: PriceData
		}
	}
}
</script>

<style lang="scss" scoped>
.price-grid {
	display: flex;
	flex-direction: column;
	grid-row-gap: 40px;

	&__item {
		display: flex;
		align-items: flex-end;

		@media (max-width: $md) {
			justify-content: space-between;
			align-items: center;
		}
	}

	&__title {
		@include h2;
		white-space: nowrap;
		line-height: 100%;

		@media (max-width: $lg) {
			font-weight: 700;
			font-size: 16px;
			line-height: 21px;
		}

		@media (max-width: $md) {
			font-weight: 700;
			font-size: 14px;
			line-height: 19px;
			white-space: normal;
			margin-right: 50px;
		}
	}

	&__dashed {
		width: 100%;
		border-bottom: 1px dashed $pink--deep-dop;

		@media (max-width: $md) {
			display: none;
		}
	}

	&__cost {
		@include h2;
		white-space: nowrap;
		line-height: 100%;
		color: $pink--deep-dop;

		@media (max-width: $lg) {
			line-height: 90%;
		}
	}
}
</style>