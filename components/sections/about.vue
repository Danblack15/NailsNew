<template>
	<div class="about">
		<img 
			src="/img/arms2.png" 
			alt="ногти" 
			class="about__arms"
		/>
		<section class="about__inside">
			<generalSlider class="about__slider" v-if="isInit"/>

			<div class="about__info">
				<h1 class="about__info-title">Привет, я Саша</h1>
				<p class="about__info-text">
					Давно выяснено, что при оценке дизайна и композиции читаемый<br />
					Текст мешает сосредоточиться. Lorem Ipsum используют потому, что тот обеспечивает более или менее.<br />
					Давно выяснено, что при оценке дизайна и композиции читаемый<br />
					Текст мешает сосредоточиться. Lorem Ipsum используют потому, что тот обеспечивает более или менее.
				</p>
			</div>
		</section>
	</div>
</template>

<script>
import generalSlider from '~/components/general/generalSlider'
export default {
	components: {
		generalSlider
	},

	data() {
		return {
			isInit: false
		}
	},

	mounted() {
		this.isInit = true
	}
}
</script>

<style lang="scss" scoped>
.about {
	position: relative;

	&__inside {
		padding: 0 66px;

		display: flex;
		justify-content: space-between;
		align-items: center;
		grid-column-gap: 65px;

		@media (max-width: $xxl) {
			grid-column-gap: 30px;
			padding: 0 36px;
		}

		@media (max-width: $xl) {
			grid-column-gap: 16px;
		}

		@media (max-width: $md) {
			flex-direction: column;
			align-items: flex-start;
			grid-row-gap: 12px;
			padding: 0 16px;
		}
	}

	&__slider {
		min-width: 570px;
		width: 570px;
		height: 566px;
		background: #EA7B81;
		overflow: hidden;

		@media (max-width: $xxl) {
			min-width: 500px;
			width: 500px;
			height: 496px;
		}

		@media (max-width: $xl) {
			min-width: 450px;
			width: 450px;
			height: 446px;
		}

		@media (max-width: $lg) {
			min-width: 316px;
			width: 316px;
			height: 313px;
		}

		@media (max-width: $md) {
			min-width: 100%;
			width: 100%;
			height: 500px;
		}

		@media (max-width: $sm) {
			height: 350px;
		}
	}

	&__info {
		max-width: 50%;

		display: flex;
		flex-direction: column;
		grid-row-gap: 24px;

		@media (max-width: $md) {
			grid-row-gap: 12px;
			max-width: 100%;
		}

		@media (max-width: $sm) {
			text-align: center;
		}
	}

	&__info-title {
		@include h1;

		@media (max-width: $lg) {
			@include h1--tablet;
		}

		@media (max-width: $sm) {
			@include h2;
		}
	}

	&__info-text {
		@include p;

		@media (max-width: $lg) {
			@include nav-mobile;
		}
	}

	&__arms {
		position: absolute;
		left: 0;
		top: 50%;
		transform: translate(-52%, -50%);

		@media (max-width: $xxl) {
			display: none;
		}
	}

}
</style>