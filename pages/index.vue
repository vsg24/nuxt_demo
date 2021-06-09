<template>
	<div class="container-fluid">
		<div class="row">
			<div class="col-xl-6 col-12">
				<section class="info-text-container">
					<h1>Find your community</h1>
				</section>
				<b-card class="nationalities-card">
					<b-card-text class="text-strong">1. Choose your nationality<b-icon-search class="search-btn" /></b-card-text>
					<b-card-text class="small text-muted">or nationality you are interested in viewing their businesses</b-card-text>
					<div class="row row-cols-2 row-cols-xl-5">
						<CountryFlag v-for="(item, index) in nationalitiesList" :key="index" class="col" :country="item" :group="'interested-nationalities'" display-type="flex-column" />
					</div>
					<div class="text-center">
						<a href="#">Show all nationalities</a>
					</div>
				</b-card>
			</div>
			<div class="col-xl-6 col-12">
				<section class="info-text-container">
					<h4>Why community matters?</h4>
					<p>Your community is important since you can find a group of people with the same language, common culture and similar needs.</p>
				</section>
				<b-card class="map-card">
					<b-card-text class="text-strong">2. Set the location<b-icon-search class="search-btn" /></b-card-text>
					<b-card-text class="small text-muted">you are interested in viewing their businesses</b-card-text>
					<div class="row">
						<div class="col-12 m-0 p-0">
							<Map />
						</div>
					</div>
				</b-card>
			</div>
		</div>
		<br>
		<div class="row">
			<div class="col-12">
				<b-card title="3. Pick a community">
					<b-card-text class="small text-muted">when you choose a community, we show its businesses</b-card-text>
					<div class="row row-cols-2">
						<CountryFlag v-for="(item, index) in communitiesList" :key="index" class="col my-1" :country="item.country" :second-country="item.secondCountry" :group="'community'" display-type="flex-row">
							<template #top>
								<div class="col-12 text-right"><a class="text-accent" href="#">Show its businesses</a></div>
							</template>
						</CountryFlag>
					</div>
				</b-card>
			</div>
		</div>
		<br>
		<div class="row">
			<div class="col-12">
				<h3 class="pb-4">Some other communities to check:</h3>
				<div class="row row-cols-2 row-cols-xl-5">
					<div class="col" v-for="(i, index) in 5" :key="index">
						<CountryFlag style="background-color: #eeebea; border-radius: .4rem;" :country="communitiesList[3].country" :second-country="communitiesList[1].secondCountry" :minimal="true" :max-width-flag="true" display-type="flex-column">
							<template #bottom>
								<div class="col-12 text-center bg-white"><a class="text-accent" href="#">Show its businesses</a></div>
							</template>
						</CountryFlag>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
import CountryFlag from "~/components/CountryFlag";
import { BIcon, BIconSearch } from 'bootstrap-vue';

export default {
	components: {
		CountryFlag,
		BIcon,
		BIconSearch
	},
	data: function() {
		return {
			nationalitiesList: [
				{name: 'Germany', title: 'German'},
				{name: 'Canada', title: 'Canadian'},
				{name: 'Spain', title: 'Spanish'},
				{name: 'Iran', title: 'Iranian'},
				{name: 'USA', title: 'American'},
				{name: 'Germany', title: 'German'},
				{name: 'Canada', title: 'Canadian'},
				{name: 'Spain', title: 'Spanish'},
				{name: 'Iran', title: 'Iranian'},
				{name: 'USA', title: 'American'},
			],
			communitiesList: [
				{
					country: {
						name: 'Germany',
						title: 'Germans'
					},
					secondCountry: {
						name: 'Canada',
						province: 'Alberta',
						city: 'Edmonton'
					}
				},
				{
					country: {
						name: 'Germany',
						title: 'Germans'
					},
					secondCountry: {
						name: 'Canada',
						province: 'Alberta',
						city: 'Edmonton'
					}
				},
				{
					country: {
						name: 'Spain',
						title: 'Spanish'
					},
					secondCountry: {
						name: 'Canada',
						province: 'Alberta',
						city: 'Edmonton'
					}
				},
				{
					country: {
						name: 'Iran',
						title: 'Iranians'
					},
					secondCountry: {
						name: 'Canada',
						province: 'Alberta',
						city: 'Edmonton'
					}
				},
				{
					country: {
						name: 'USA',
						title: 'Americans'
					},
					secondCountry: {
						name: 'Canada',
						province: 'Alberta',
						city: 'Edmonton'
					}
				},
				{
					country: {
						name: 'Germany',
						title: 'Germans'
					},
					secondCountry: {
						name: 'Canada',
						province: 'Alberta',
						city: 'Edmonton'
					}
				},
			]
		}
	},
	mounted() {

	}
}
</script>

<style>
	.info-text-container {
		margin: 2rem 0;
		min-height: 5rem;
	}

	.nationalities-card, .map-card {
		height: 450px;
	}

	.search-btn {
		position: absolute;
		right: 1rem;
		top: 1.7rem;
	}

	@media(max-width: 1200px) {
		.nationalities-card, .map-card {
			height: auto;
		}
	}
</style>
