<template>
	<div class="work-grid">
		<GridItem 
			class="work-grid__item" 
			v-for="work in myWorks" 
			:key="work.if"
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
		width: 265px;
		height: 265px;
	}
}
</style>