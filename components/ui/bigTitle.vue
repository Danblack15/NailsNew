<template>
	<div class="big-title">
		<div class="big-title__line"></div>

		<p class="big-title__inner">
			<span
				v-for="(letter, i) in value"
				:key="letter + i"
				class="big-title__letter"
			>
				{{ letter }}
			</span>
		</p>

		<div class="big-title__line"></div>
	</div>
</template>

<script>
export default {
	props: {
		value: {
			type: String,
			required: true
		}
	},

}
</script>

<style lang="scss" scoped>
.big-title {
	display: flex;
	align-items: center;

	&__inner {
		@include big-title;

		display: flex;
		justify-content: center;

		margin: 0 24px;

		@media (max-width: $lg) {
			@include h1--tablet;
			margin: 0 16px;
		}

		@media (max-width: $md) {
			font-size: 32px;
			margin: 0 12px;
		}
	}

	&__letter {
		text-transform: uppercase;
		display: flex;
		align-items: center;

		&::after {
			content: '';
			display: block;
			min-width: 20px;
			height: 2px;
			background: $pink--deep-light-dop1;
			margin: 0 24px;

			@media (max-width: $lg) {
				margin: 0 16px;
			}

			@media (max-width: $md) {
				margin: 0 12px;
			}
		}

		&:last-child {
			&::after {
				display: none;
			}
		}
	}

	&__line {
		width: 100%;
		height: 2px;
		background: $pink--deep-light-dop1;
	}
}
</style>