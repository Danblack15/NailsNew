<template>
	<button class="button">
		<p class="button__text">
			<slot></slot>
		</p>
		<span class="button__liquid"></span>
	</button>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.button {
	@include h2;

	position: relative;
	color: #0D3F7C;
	padding: 21px 137px;
	border-radius: 50px;
	border: none;
	overflow: hidden;
	cursor: pointer;

	@media (max-width: $lg) {
		@include nav-mobile;
		font-weight: 700;
		padding: 8px 74px;
	}

	&:hover {
		.button__liquid {
			top: -140px;
		}
	}

	&__text {
		position: relative;
		z-index: 2;
	}

	&__liquid {
		position: absolute;
		top: -50px;
		left: 0;
		width: 100%;
		height: 245px;
		background: #E88A8A;
		transition: 1s;

		&::after {
			content: '';
			width: 180%;
			height: 320%;
			position: absolute;
			top: 0;
			left: 50%;
			transform: translate(-50%, -75%);

			border-radius: 40%;
			background: rgba(255, 255, 255, 0.322);
			animation: animate 10s linear infinite;
			z-index: 1;

			@media (max-width: $lg) {
				width: 210%;
				height: 190%;
			}
		}

		&::before {
			content: '';
			width: 180%;
			height: 320%;
			position: absolute;
			top: 0;
			left: 50%;
			transform: translate(-50%, -75%);

			border-radius: 45%;
			background: rgba(254, 243, 243, 0.203);
			animation: animate 5s linear infinite;

			@media (max-width: $lg) {
				width: 210%;
				height: 190%;
			}
		}

	}

	@keyframes animate {
		0% {
			transform: translate(-50%, -88%) rotate(0deg);
		}

		100% {
			transform: translate(-50%, -88%) rotate(360deg);
		}
	}
}
</style>