<template>
	<div 
		class="grid-item" 
		@click="showDescription"
	>
		<div 
			:class="['grid-item__img', {
				'grid-item__img--close': showDesc
			}]" 
			:style="{ background: randomBackground() }"
		>
			<img 
				:src="imgLink(work.link)" 
				alt="ногти" 
				class=""
			/>
		</div>
		<div :class="['grid-item__modal', {
			'grid-item__modal--open': showDesc
		}]">
			<p :class="['grid-item__modal-text', {
				'grid-item__modal-text--show': showDesc
			}]">{{ work.desc }}</p>
		</div>
	</div>
</template>

<script>
export default {
	props: {
		work: {
			type: Object,
			default: null
		}
	},

	data() {
		return {
			showDesc: false
		}
	},

	methods: {
		randomBackground() {
			const backs = ['rgba(234, 123, 129, 0.6)', 'rgba(191, 79, 78, 0.6)']
			return backs[Math.floor(Math.random() * backs.length)]
		},

		showDescription() {
			this.showDesc = !this.showDesc
		},

		imgLink(link) {
			const types = ['png', 'jpg', 'jpeg']

			let http = new XMLHttpRequest()

			for (let i = 0; i < types.length; i++) {
				const type = types[i];
				
				http.open('HEAD', `${link}.${type}`, false)
				http.send()
				
				if (http.status != 404)
					return link+'.'+type
			}
		}
	}
}
</script>

<style lang="scss" scoped>
.grid-item {
	position: relative;
	perspective: 500px;
	transition: .2s transform;
	cursor: pointer;

	@media (min-width: $md) {
		&:hover {
			transform: scale(1.05);
		}
	}


	&__img {
		position: relative;
		width: 100%;
		height: 100%;
		transform-style: preserve-3d;
		transition: .7s all;
		backface-visibility: hidden;

		&--close {
			transform: rotateY(-180deg);
		}

		& img {
			position: absolute;
			top: 0;
			left: 0;
			width: 100%;
			height: 100%;
			object-fit: cover;
		}
	}

	&__modal {
		position: absolute;
		width: 100%;
		height: 100%;
		top: 0;
		left: 0;
		background: rgba(13, 63, 124, 0.6);;
		display: flex;
		justify-content: center;
		align-items: center;
		padding: 0 15px;
		backface-visibility: hidden;

		transform: rotateY(180deg);
		transform-style: preserve-3d;
		visibility: hidden;
		transition: .7s all;

		@media (max-width: $lg) {
			padding: 0 5px;
		}

		&--open {
			opacity: 1;
			visibility: visible;
			transform: rotateY(0);
		}
	}

	&__modal-text {
		@include desc;
		color: $pink--light;
		text-align: center;
		opacity: 0;
		transition: .2s;

		@media (max-width: $lg) {
			@include nav-mobile;
			font-weight: 700;
		}

		&--show {
			opacity: 1;
			transition: .4s;
		}
	}
}
</style>