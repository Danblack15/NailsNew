<template>
	<div class="general">
		<img 
			src="/img/arms1.png" 
			alt="arms" 
			class="general__arms" 
		/>

		<section class="general__inside">
			<h1 class="general__title">Намитова Александра</h1>
			<p class="general__text">Давно выяснено, что при оценке дизайна и композиции читаемый<br />
				Текст мешает сосредоточиться. Lorem Ipsum используют что тот обеспечивает более или менее</p>
			<buttonUI>Записаться</buttonUI>
			<div class="general__contacts">
				<h2 class="general__subtitle">Больше информации:</h2>
				<ul class="general__contacts-list">
					<a href="#" class="general__contacts-src">
						<li class="general__contacts-item">
							<img src="/img/icons/instagram.svg" alt="инстаграм" />
						</li>
					</a>
					<a href="#" class="general__contacts-src">
						<li class="general__contacts-item">
							<img src="/img/icons/vk.svg" alt="вконтакте" />
						</li>
					</a>
					<a href="#" class="general__contacts-src">
						<li class="general__contacts-item">
							<img src="/img/icons/telegram.svg" alt="телеграм" />
						</li>
					</a>
					<a href="#" class="general__contacts-src">
						<li class="general__contacts-item">
							<img src="/img/icons/whatsapp.svg" alt="ватсап" />
						</li>
					</a>
				</ul>
			</div>
		</section>

		<img 
			src="/img/promo.png" 
			alt="promo" 
			class="general__promo" 
		/>
	</div>
</template>

<script>
import buttonUI from '~/components/ui/buttonUI';
export default {
	components: {
		buttonUI
	}
}
</script>

<style lang="scss" scoped>
.general {
	@media (max-width: $md) {
		display: flex;
		flex-direction: column-reverse;
		align-items: center;
	}

	&__promo {
		position: absolute;
		top: 0;
		right: 0;
		z-index: 0;
		
		@media (max-width: $xxl) {
			width: 600px;
			top: 10px;
		}

		@media (max-width: $lg) {
			width: 400px;
			top: 20px;
		}

		@media (max-width: $md) {
			top: 0;
			position: relative;
			max-width: 100%;
		}
	}

	&__inside {
		padding: 138px 0 0 66px;
		z-index: 1;
		position: relative;

		@media (max-width: $xxl) {
			padding: 36px 0 0 36px;
		}

		@media (max-width: $md) {
			text-align: center;
			padding: 0 16px;
			margin-top: 17px;
		}
	}

	&__title {
		@include h1;

		@media (max-width: $lg) {
			@include h1--tablet;
		}

		@media (max-width: $sm) {
			@include h2;
		}
	}

	&__text {
		@include p;
		margin: 24px 0;
		max-width: 540px;

		@media (max-width: $lg) {
			margin: 12px 0;
			max-width: 350px;
			@include nav-mobile;
		}

		@media (max-width: $md) {
			max-width: 450px;
			margin: 12px auto;
		}
	}

	&__subtitle {
		@include h2;

		@media (max-width: $lg) {
			@include nav;
		}

		@media (max-width: $sm) {
			@include nav-mobile;
			font-weight: 700;
		}
	}

	&__contacts {
		display: flex;
		flex-direction: column;
		grid-row-gap: 35px;
		margin-top: 35px;

		@media (max-width: $lg) {
			grid-row-gap: 12px;
			margin-top: 24px;
		}

		@media (max-width: $md) {
			align-items: center;
			margin-top: 16px;
		}
	}

	&__contacts-list {
		display: flex;
		grid-column-gap: 24px;

		@media (max-width: $lg) {
			grid-column-gap: 13px;
		}
	}

	&__contacts-src {
		transition: .2s transform;
		&:hover {
			transform: scale(1.1);
		}
	}
	
	&__contacts-item {
		width: 64px;
		height: 64px;
		border-radius: 50%;
		background: $pink--deep-light;
		display: flex;
		justify-content: center;
		align-items: center;

		@media (max-width: $lg) {
			width: 36px;
			height: 36px;

			& img {
				transform: scale(0.6);
			}
		}
	}

	&__arms {
		position: absolute;
		top: 0;
		left: 0;
		transform: translate(-40%, -40%);

		@media (max-width: $xxl) {
			display: none;
		}

		@media (max-width: $md) {
			display: block;
			width: 140px;
			left: 20px;
		}
	}
}
</style>