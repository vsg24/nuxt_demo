<template>
	<header class="container-fluid">
		<div class="row h-100">
			<div class="col-xl-4 col-lg-4 col-12 d-flex align-items-center justify-content-xl-start justify-content-center">
				<b-img class="logo ml-xl-5" src="/nuxtjs-typo-white.svg" />
			</div>
			<div class="col-xl-4 col-lg-4 col-10 d-flex align-items-center justify-content-center">
				<autocomplete
					class="w-75"
					:search="search"
					placeholder="I need to" />
			</div>
			<div class="col-xl-4 col-lg-4 col-2 d-flex align-items-center justify-content-end">
				<b-avatar class="mr-xl-5" badge="24" variant="primary" badge-variant="danger" size="60px" src="https://placekitten.com/300/300"></b-avatar>
			</div>
		</div>
	</header>
</template>

<script>
import Autocomplete from '@trevoreyre/autocomplete-vue';
import '@trevoreyre/autocomplete-vue/dist/style.css'

export default {
	components: {
		Autocomplete
	},
	data() {
		return {
			actions: [
				'Find businesses',
				'Search advertisements'
			]
		}
	},
	methods: {
		search(input) {
			if (input.length < 1) { return [] }
			return this.actions.filter(action => {
				return action.toLowerCase().startsWith(input.toLowerCase());
			})
		}
	}
}
</script>

<style>
	header.container-fluid {
		background-image: linear-gradient(#153243, #3b5160);
		height: 8rem;
	}

	.logo {
		max-width: 15rem;
	}

	.autocomplete-input {
		background: transparent;
	}

	.autocomplete-input {
		border: 1px solid #eee;
		border-radius: 8px;
		width: 100%;
		padding: 12px 12px 12px 12px;
		box-sizing: border-box;
		position: relative;
		font-size: 16px;
		line-height: 1.5;
		flex: 1;
		background-color: transparent;
		background-image: url("/angle_down.png");
		background-size: 15px;
		background-repeat: no-repeat;
		background-position: 95%;
	}
</style>
