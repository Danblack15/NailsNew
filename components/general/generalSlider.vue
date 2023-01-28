<template>
	<div class="slider swiper">
		<div class="swiper-wrapper slider__wrapper">
			<div 
			v-for="nail in allNails"
			:key="nail.id"
				class="swiper-slide slider__item"
			>
				<img 
					:src="imgLink(nail.link)" 
					alt="nails" 
					class="slider__item-img"
				/>
			</div>
		</div>

		<div class="swiper-pagination slider__pagination"></div>

		<div class="slider__navigation">
			<div class="slider__btn slider__btn-prev">
				<img src="/img/icons/white-small-arrow.svg" alt="назад" />
			</div>
			<div class="slider__btn slider__btn-next">
				<img src="/img/icons/white-small-arrow.svg" alt="вперед" />
			</div>
		</div>
	</div>
</template>

<script>

import Nails from '~/data/enums/sliderNails'
import Swiper, { Navigation, Pagination } from 'swiper';
import 'swiper/swiper.scss';
import 'swiper/components/navigation/navigation.scss';
import 'swiper/components/pagination/pagination.scss';

Swiper.use([Navigation, Pagination])
export default {
	data() {
		return {
			allNails: Nails
		}
	},

	mounted() {
		const swiper = new Swiper('.swiper', {
			modules: [Navigation, Pagination],
			pagination: {
				el: '.swiper-pagination',
				clickable: true,
				dynamicBullets: true
			},
			navigation: {
				nextEl: '.slider__btn-next',
				prevEl: '.slider__btn-prev',
			},
			loop: true
		})
	},

	methods: {
		imgLink(link) {
			const types = ['png', 'jpg', 'jpeg']

			let http = new XMLHttpRequest()

			for (let i = 0; i < types.length; i++) {
				const type = types[i];
				
				http.open('HEAD', `${link}.${type}`, false)
				http.send()
				
				if (http.status != 404)
					return link+'.'+type

				// var img = new Image()
				// img.src = link+'.'+type
				// if (img.height != 0)
				// 	return link+'.'+type
			}
		}
	}
}
</script>

<style lang="scss" scoped>
.slider {
	position: relative;

	&__wrapper {}

	&__navigation {
		width: 100%;
		position: absolute;

		bottom: 20px;
		margin: 0 auto;
		padding: 0 32px;

		display: flex;
		justify-content: space-between;

		z-index: 2;
	}

	&__btn {
		width: 64px;
		height: 64px;
		background: $beige;
		display: flex;
		justify-content: center;
		align-items: center;
		border-radius: 50%;
		cursor: pointer;
		transition: .2s all;

		&:hover {
			transform: scale(1.1);
			background: #F8B9BC;
		}
	}

	&__btn-next {
		& img {
			transform: rotate(180deg);
		}
	}

	&__pagination {
		bottom: 44px;
	}

	&__item {
		width: 100%;
		height: 100%;
		position: relative;
	}

	&__item-img {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	::v-deep .swiper-pagination-bullet {
		width: 10px;
		height: 10px;
		background: #A4A1A0;
		opacity: 1;
		transform: scale(1);
		margin: 3px 8px;

		&-active {
			width: 16px;
			height: 16px;
			background: #193A6A;
			transform: scale(1);
			margin: 0 8px;
		}
	}
}
</style>