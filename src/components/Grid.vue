<template>
	<section>
		<div class="container">
			<div class="container-box" v-if="data">
				<template v-for="(album, index) in data">
					<Card :key="`card-${index}`" :poster="album.poster" :title="album.title" :author="album.author" :year="album.year" :genre="album.genre" />
				</template>
			</div>
			<Loader v-else />
		</div>
	</section>
</template>

<script>
import Card from "./Card.vue";
import Loader from "./Loader.vue";
export default {
	components: { Card, Loader },
	name: "Grid",
	props: {
		data: Array,
	},
	data() {
		return {
			list: null,
		};
	},
	methods: {},
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
