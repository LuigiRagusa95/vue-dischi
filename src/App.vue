<template>
	<div id="app">
		<Header :data="data" @filterFor="filterGenre" />
		<Grid :data="data" :filter="currentValueToFilter" />
	</div>
</template>

<script>
import axios from "axios";

import Grid from "./components/Grid.vue";
import Header from "./components/Header.vue";
export default {
	name: "App",
	created() {
		this.getData();
	},
	data() {
		return {
			data: null,
			currentValueToFilter: "",
		};
	},
	components: { Header, Grid },
	methods: {
		getData() {
			setTimeout(() => {
				axios.get("https://flynn.boolean.careers/exercises/api/array/music").then((response) => {
					this.data = response.data.response;
				});
			}, 2000);
		},
		filterGenre(value) {
			this.currentValueToFilter = value;
		},
	},
};
</script>

<style lang="scss">
*,
*::before,
*::after {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}
html,
body {
	width: 100%;
	height: 100%;
	font-family: sans-serif;
	background: #1d2d3c;
}
</style>
