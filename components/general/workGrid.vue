<template>
	<div class="work-grid">
		<GridItem 
			class="work-grid__item" 
			v-for="work in myWorks" 
			:key="work.id"
			:work="work"
		/>
	</div>
</template>

<script>
import myWork from '~/data/enums/myWork'

import GridItem from '~/components/ui/gridItem'

export default {
	components: {
		GridItem
	},

	data() {
		return {
			myWorks: myWork
		}
	}
}
</script>

<style lang="scss" scoped>
.work-grid {
	display: flex;
	flex-wrap: wrap;
	justify-content: space-between;
	grid-column-gap: 25px;
	grid-row-gap: 30px;

	&__item {
		width: 256px;
		height: 256px;

		@media (max-width: $lg) {
			width: 150px;
			height: 150px;
		}
	}
}
</style>