<template>
	<header class="header">
		<div class="header__inside">
			<div class="header__logo-block">
				<img src="/img/icons/logo.svg" alt="logo" class="header__logo" />
				<p class="header__logo-text">
					<span>namitova</span>.nails
				</p>
			</div>

			<nav class="header__navigation">
				<ul class="header__navigation-list" id="menu">
					<li class="header__navigation-item" data-menuanchor="firstPage">
						<a href="#generalBlock">Главная</a>
					</li>
					<li class="header__navigation-item" data-menuanchor="secondPage">
						<a href="#aboutBlock">Обо мне</a>
					</li>
					<li class="header__navigation-item" data-menuanchor="portfolioBlock">
						<a href="#portfolioBlock">Мои работы</a>
					</li>
					<li class="header__navigation-item" data-menuanchor="priceBlock">
						<a href="#priceBlock">Прайс</a>
					</li>
					<li class="header__navigation-item" data-menuanchor="regisrBlock">
						<a href="#regisrBlock">Запись</a>
					</li>
				</ul>
			</nav>
		</div>
	</header>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.header {
	width: 100%;
	padding: 20px 165px;

	background: $pink--light;

	&__inside {
		max-width: 1440px;
		margin: 0 auto;

		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	&__logo-block {
		display: flex;
		align-items: center;
		grid-column-gap: 5px;
	}

	&__logo-text {
		font-family: 'Mali';
		font-weight: 400;
		font-size: 24px;
		line-height: 31px;

		& span {
			font-family: inherit;
			color: $pink--deep;
		}
	}

	&__navigation-list {
		display: flex;
		margin-right: 138px;
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
}
</style>