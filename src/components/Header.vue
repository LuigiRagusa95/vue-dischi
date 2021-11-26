<template>
	<header>
		<div class="logo">
			<a href="#"><img src="../assets/logo.png" alt="brand-logo" /></a>
		</div>
		<select v-model="valueSelected" @change="$emit('filterFor', valueSelected)">
			<option value="">All</option>
			<option :value="d.genre" v-for="(d, index) in unique" :key="`opt-${index}`">{{ d.genre }}</option>
		</select>
	</header>
</template>

<script>
export default {
	name: "Header",
	props: {
		data: Array,
	},
	computed: {
		unique() {
			return this.data.filter((el, i, arr) => arr.findIndex((v) => v.genre === el.genre) === i);
		},
	},
	data() {
		return {
			valueSelected: "",
		};
	},
};
</script>

<style lang="scss" scoped>
header {
	display: flex;
	padding: 5px 10px;
	background: #2e3a46;
	align-items: center;
	justify-content: space-between;
}

header .logo {
	width: 3rem;
	height: 3rem;
	display: flex;
	overflow: hidden;
	align-items: center;
	justify-content: center;
}

header .logo > a > img {
	width: 100%;
	object-fit: contain;
}
</style>
