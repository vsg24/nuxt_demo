<template>
	<div>
		<div v-if="selected" class="row"><slot name="top"></slot></div>
		<div @click="select" :class="{'selected': selected}" class="d-flex flex-column text-center align-items-center">
			<div class="row w-100">
				<div class="col"><Country :data="country" :display-type="displayType" :max-width-flag="maxWidthFlag" /></div>
				<span class="col-xl-1 col-12 d-flex justify-content-center align-items-center" v-if="secondCountry">of</span>
				<div class="col"><Country v-if="secondCountry" :data="secondCountry" :minimal="minimal" :display-type="displayType" :max-width-flag="maxWidthFlag" /></div>
				<div v-if="selected" class="checked-icon"><b-icon-check /></div>
			</div>
		</div>
		<div v-if="selected" class="row"><slot name="bottom"></slot></div>
	</div>
</template>

<script>
import Country from "~/components/Country";
import { BIcon, BIconCheck } from 'bootstrap-vue';
import EventBus from "~/EventBus";

export default {
	props: ['displayType', 'country', 'secondCountry', 'group', 'minimal', 'maxWidthFlag'],
	components: {
		Country,
		BIcon,
		BIconCheck
	},
	data() {
		return {
			selected: false
		}
	},
	methods: {
		select() {
			this.selected = !this.selected;
			EventBus.$emit('country-flag-selected', {group: this.group, id: this._uid});
		}
	},
	created() {
		EventBus.$on('country-flag-selected', (data) => {
			if(data.group === this.group && this._uid !== data.id) {
				let id = this._uid;
				this.selected = false;
			}
		});
	}
}
</script>

<style scoped>
	.d-flex {
		padding: .6rem .4rem;
	}

	.d-flex:hover, .selected {
		background: var(--accent-color);
		cursor: pointer;
		border-radius: .4rem;
		color: #fff;
		transition: .2s;
	}

	.checked-icon {
		position: absolute;
		top: 0;
		right: 15px;
	}
</style>
