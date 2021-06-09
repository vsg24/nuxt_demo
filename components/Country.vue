<template>
	<div class="d-flex align-items-center" :class="displayType">
		<b-img class="flag" :class="{'w-100': maxWidthFlag}" :src="`/flags/${data.name}.png`" />
		<span :class="{'ml-3': displayType === 'flex-row', 'mt-2': displayType === 'flex-column'}">{{ getTitle(data) }}</span>
	</div>
</template>

<script>

export default {
	props: ['data', 'minimal', 'displayType', 'maxWidthFlag'],
	methods: {
		getTitle(country) {
			let res = '';

			if(!this.minimal) {
				if(country.city != null) {
					res += `${country.city}, `
				}

				if(country.province != null) {
					res += `${country.province}, `
				}
			}

			return res + `${country.title ?? country.name}`;
		}
	}
}
</script>

<style scoped>
.flag {
	height: 60px;
	width: 120px;
	object-fit: cover;
}
</style>
