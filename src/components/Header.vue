<template>
	<header>
		<div class="logo">
			<a href="#"><img src="../assets/logo.png" alt="brand-logo" /></a>
		</div>
		<Select />
	</header>
</template>

<script>
import Select from "./Select.vue";
export default {
	components: { Select },
	name: "Header",
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
