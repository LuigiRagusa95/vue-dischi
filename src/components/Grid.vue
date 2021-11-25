<template>
	<section>
		<div class="container">
			<div class="container-box" v-if="list">
				<template v-for="(album, index) in list">
					<Card :key="`card-${index}`" :poster="album.poster" :title="album.title" :author="album.author" :year="album.year" :genre="album.genre" />
				</template>
			</div>
			<Loader v-else />
		</div>
	</section>
</template>

<script>
import axios from "axios";

import Card from "./Card.vue";
import Loader from "./Loader.vue";
export default {
	components: { Card, Loader },
	name: "Grid",
	data() {
		return {
			list: null,
		};
	},
	methods: {
		getData() {
			setTimeout(() => {
				axios.get("https://flynn.boolean.careers/exercises/api/array/music").then((response) => {
					this.list = response.data.response;
				});
			}, 2000);
		},
	},
	created() {
		this.getData();
	},
};
</script>

<style lang="scss" scoped>
section {
	display: flex;
	flex-direction: column;

	& .container {
		display: flex;
		min-height: 100vh;
		align-items: center;
		justify-content: center;

		&-box {
			flex-grow: 1;
			display: flex;
			padding: 10px;
			margin: 0 auto;
			flex-wrap: wrap;
			max-width: 1400px;
			align-items: center;
			justify-content: center;
		}
	}
}
</style>
