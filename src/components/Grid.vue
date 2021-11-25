<template>
	<section>
		<div class="container">
			<Card />
		</div>
	</section>
</template>

<script>
import axios from "axios";

import Card from "./Card.vue";
export default {
	components: { Card },
	name: "Grid",
};
</script>

<style lang="scss" scoped>
.container {
	display: flex;
	padding: 10px;
	margin: 0 auto;
	flex-wrap: wrap;
	max-width: 1400px;
}
</style>
