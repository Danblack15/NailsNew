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
	
	&:hover {
		transform: scale(1.05);
	}

	&__img {
		width: 100%;
		height: 100%;
		transform-style: preserve-3d;
		transition: .4s all;

		&--close {
			transform: rotateY(-180deg);
			opacity: 0;
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

		transform: rotateY(180deg);
		transform-style: preserve-3d;
		opacity: 0;
		visibility: hidden;
		transition: .4s all;

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

		&--show {
			opacity: 1;
			transition: .4s;
		}
	}
}
</style>