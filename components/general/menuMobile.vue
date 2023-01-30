<template>
	<div class="menu">
		<nav class="menu__nav">
			<ul class="menu__navigation">
				<li class="menu__navigation-item">
					<a href="#generalBlock">Главная</a>
				</li>
				<li class="menu__navigation-item">
					<a href="#aboutBlock">Обо мне</a>
				</li>
				<li class="menu__navigation-item">
					<a href="#portfolioBlock">Мои работы</a>
				</li>
				<li class="menu__navigation-item">
					<a href="#priceBlock">Прайс</a>
				</li>
				<li class="menu__navigation-item">
					<a href="#regisrBlock">Запись</a>
				</li>
			</ul>
		</nav>

		<ul class="menu__contacts">
			<a href="#" class="menu__contacts-link">
				<li class="menu__contacts-item">
					<img src="/img/icons/instagram.svg" alt="инстаграм" />
				</li>
			</a>
			<a href="#" class="menu__contacts-link">
				<li class="menu__contacts-item">
					<img src="/img/icons/vk.svg" alt="вконтакте" />
				</li>
			</a>
			<a href="#" class="menu__contacts-link">
				<li class="menu__contacts-item">
					<img src="/img/icons/telegram.svg" alt="телеграм" />
				</li>
			</a>
			<a href="#" class="menu__contacts-link">
				<li class="menu__contacts-item">
					<img src="/img/icons/whatsapp.svg" alt="ватсап" />
				</li>
			</a>
		</ul>
	</div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.menu {
	background: $pink--light;

	&__nav {
		width: 100%;
	}

	&__navigation {
		display: flex;
		flex-direction: column;
		align-items: center;
		width: 536px;
		margin: 0 auto;

		@media (max-width: $md) {
			width: 100%;
		}
	}

	&__navigation-item {
		@include h2;
		color: $blue;
		width: 100%;
		text-align: center;
		font-weight: 400;

		@media (max-width: $md) {
			@include nav-mobile;
		}

		& a {
			font-family: 'Nunito';
			width: 100%;
			display: block;
			padding: 12px 0;
		}

		&:first-child a {
			padding-top: 0;
		}

		&::after {
			content: '';
			display: block;
			width: 100%;
			height: 1px;
			background: $pink--deep-light-dop;
		}
	}

	&__contacts {
		display: flex;
		grid-column-gap: 18px;
		margin-top: 25px;

		@media (max-width: $md) {
			margin-top: 15px;
		}
	}

	&__contacts-item {
		width: 48px;
		height: 48px;
		background: $pink--deep-light;
		border-radius: 50%;
		display: flex;
		justify-content: center;
		align-items: center;

		@media (max-width: $md) {
			width: 36px;
			height: 36px;
		}

		& img {
			transform: scale(0.8);

			@media (max-width: $md) {
				transform: scale(0.6);
			}
		}
	}
}
</style>