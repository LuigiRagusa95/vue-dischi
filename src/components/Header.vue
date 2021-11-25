<template>
	<header>
		<div class="logo">
			<a href="#"><img src="../assets/logo.png" alt="brand-logo" /></a>
		</div>
	</header>
</template>

<script>
export default {
	name: "Header",
};
</script>

<style lang="scss" scoped>
header {
	padding: 5px 10px;
	background: #2e3a46;
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
