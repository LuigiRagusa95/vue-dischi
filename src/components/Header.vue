<template>
	<header>
		<div class="logo">
			<a href="#"><img src="../assets/logo.png" alt="brand-logo" /></a>
		</div>
		<select v-model="valueSelected" @change="$emit('getGenre', valueSelected)">
			<option value="">All</option>
			<option value="rock">Rock</option>
			<option value="pop">Pop</option>
			<option value="jazz">Jazz</option>
			<option value="metal">Metal</option>
		</select>
	</header>
</template>

<script>
export default {
	name: "Header",
	data() {
		return {
			valueSelected: "",
		};
	},
	methods: {
		getValue() {
			console.log(this.valueSelected);
		},
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
