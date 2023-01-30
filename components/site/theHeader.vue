<template>
	<header class="header">
		<MenuMobile class="header__menu-mobile" :class="{'header__menu-mobile--open': showMenu}"  />
		<div class="header__inside">
			<div class="header__menu" @click="toggleMenu">
				<div class="header__menu-line"></div>
				<div class="header__menu-line"></div>
				<div class="header__menu-line"></div>
			</div>

			<div class="header__logo-block">
				<img src="/img/icons/logo.svg" alt="logo" class="header__logo" />
				<p class="header__logo-text">
					<span>namitova</span>.nails
				</p>
			</div>

			<nav class="header__navigation">
				<ul class="header__navigation-list" id="menu">
					<li class="header__navigation-item">
						<a href="#generalBlock">Главная</a>
					</li>
					<li class="header__navigation-item">
						<a href="#aboutBlock">Обо мне</a>
					</li>
					<li class="header__navigation-item">
						<a href="#portfolioBlock">Мои работы</a>
					</li>
					<li class="header__navigation-item">
						<a href="#priceBlock">Прайс</a>
					</li>
					<li class="header__navigation-item">
						<a href="#regisrBlock">Запись</a>
					</li>
				</ul>
			</nav>
		</div>
	</header>
</template>

<script>
import MenuMobile from '~/components/general/menuMobile';
export default {
	components: {
		MenuMobile
	},

	data() {
		return {
			showMenu: false
		}
	},

	methods: {
		toggleMenu () {
			this.showMenu =!this.showMenu

			let menu = document.querySelector('.header__menu-mobile')

			setTimeout(() => {
				if (this.showMenu)
					menu.style.maxHeight = menu.scrollHeight + 16 + 'px'
				else
					menu.style.maxHeight = 0
			}, 100)
		}
	}
}
</script>

<style lang="scss" scoped>
.header {
	width: 100%;
	padding: 20px 165px;

	background: $pink--light;

	@media (max-width: $xxl) {
		padding: 20px 100px;
	}

	@media (max-width: $xl) {
		padding: 18px 59px;
	}

	@media (max-width: $md) {
		padding: 22px 15px;
	}

	&__inside {
		position: relative;

		max-width: 1440px;
		margin: 0 auto;

		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	&__logo {
		@media (max-width: $md) {
			width: 30px;
			height: 30px;
		}
	}

	&__logo-block {
		display: flex;
		align-items: center;
		grid-column-gap: 5px;

		@media (max-width: $xl) {
			position: absolute;
			left: 50%;
			top: 50%;
			transform: translate(-50%, -50%);
		}
	}

	&__logo-text {
		font-family: 'Mali';
		font-weight: 400;
		font-size: 24px;
		line-height: 31px;

		@media (max-width: $md) {
			font-size: 16px;
			line-height: 21px;
		}

		& span {
			font-family: inherit;
			color: $pink--deep;
		}
	}

	&__navigation {
		@media (max-width: $xl) {
			display: none;
		}
	}

	&__navigation-list {
		display: flex;
		margin-right: 200px;

		@media (max-width: $xxl) {
			margin-right: 138px;
		}
	}

	&__navigation-item {
		display: flex;
		@include nav;

		&::after {
			content: '';
			display: block;
			position: relative;
			width: 2px;
			background: $blue;
			height: 100%;
			margin: 0 24px;
		}

		&:last-child {
			&::after {
				display: none;
			}
		}

		& a {
			font-family: 'Nunito';
		}
	}

	&__menu {
		display: none;
		flex-direction: column;
		justify-content: space-between;
		height: 24px;

		cursor: pointer;

		@media (max-width: $xl) {
			display: flex;
		}

		@media (max-width: $md) {
			height: 17px;
		}
	}

	&__menu-line {
		width: 36px;
		height: 3px;
		background: $blue;

		@media (max-width: $md) {
			width: 24px;
		}
	}

	&__menu-mobile {
		display: none;
		flex-direction: column;
		align-items: center;
		max-height: 0;
		overflow: hidden;

		left: 0;
		top: 60px;

		position: absolute;
		width: 100%;
		transition: .3s;

		&--open {
			padding: 20px 0 25px 0;

			@media (max-width: $md) {
				padding: 15px 35px 15px 35px;
			}
		}

		@media (max-width: $xl) {
			display: flex;
		}
	}
}
</style>