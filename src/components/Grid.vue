<template>
	<section>
		<div class="container">
			<template v-for="(album, index) in list">
				<Card :key="`card-${index}`" :poster="album.poster" :title="album.title" :author="album.author" :year="album.year" :genre="album.genre" />
			</template>
		</div>
	</section>
</template>

<script>
import axios from "axios";

import Card from "./Card.vue";
export default {
	components: { Card },
	name: "Grid",
	data() {
		return {
			list: null,
		};
	},
	methods: {
		getData() {
			axios.get("https://flynn.boolean.careers/exercises/api/array/music").then((response) => {
				this.list = response.data.response;
			});
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

	& .container {
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
</style>
