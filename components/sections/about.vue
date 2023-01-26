<template>
	<div class="about">
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
	&__inside {
		padding: 0 66px;

		display: flex;
		justify-content: space-between;
		align-items: center;
		grid-column-gap: 65px;
	}

	&__slider {
		min-width: 570px;
		width: 570px;
		height: 566px;
		background: #EA7B81;
		overflow: hidden;
	}

	&__info {
		max-width: 50%;

		display: flex;
		flex-direction: column;
		grid-row-gap: 24px
	}

	&__info-title {
		@include h1;
	}

	&__info-text {
		@include p;
	}

}
</style>