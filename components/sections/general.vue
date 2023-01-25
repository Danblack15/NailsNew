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
	&__promo {
		position: absolute;
		top: 0;
		right: 0;
		z-index: 0;
	}

	&__inside {
		padding: 138px 0 0 66px;
		z-index: 1;
		position: relative;
	}

	&__title {
		@include h1;
	}

	&__text {
		@include p;
		margin: 24px 0;
		max-width: 540px;
	}

	&__subtitle {
		@include h2;
	}

	&__contacts {
		display: flex;
		flex-direction: column;
		grid-row-gap: 35px;
		margin-top: 35px;
	}

	&__contacts-list {
		display: flex;
		grid-column-gap: 24px;
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
	}

	&__arms {
		position: absolute;
		top: 0;
		left: 0;
		transform: translate(-40%, -40%);
	}
}
</style>