<template>
	<div class="works-slider swiper">
		<div class="swiper-wrapper slider__wrapper">
			<div 
				class="swiper-slide works-slider__slide" 
				v-for="work in myWorks" 
				:key="work.id"
			>
				<GridItem 
					class="works-slider__item" 
					:work="work"
				/>
			</div>
		</div>
	</div>
</template>

<script>
import Swiper, {Pagination} from 'swiper';
import 'swiper/swiper.scss';
import 'swiper/components/pagination/pagination.scss';

import GridItem from '~/components/ui/gridItem'

import myWork from '~/data/enums/myWork'

Swiper.use([Pagination])
export default {
	components: {
		GridItem
	},

	data() {
		return {
			myWorks: myWork
		}
	},
	
	mounted() {
		const worksSlider = new Swiper('.works-slider', {
			slidesPerView: 1,
			spaceBetween: -60,
			breakpoints: {
				576: {
					spaceBetween: -180,
				},
				660: {
					spaceBetween: -250,
				},
			}
		})
	},
	
}
</script>

<style lang="scss" scoped>
.works-slider {
	width: 100%;

	&__slide {
		width: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	&__item {
		width: 280px;
		height: 280px;

		@media (max-width: $sm) {
			width: calc(100% - 120px);
			height: 300px;
		}

		@media (max-width: $xs) {
			height: 50vw;
		}
	}

	.swiper-slide-active {

		.works-slider__item {
			transform: scale(1.2);
		}
	}
}
</style>