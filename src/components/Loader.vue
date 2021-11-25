<template>
	<div class="screen">
		<div class="loader"></div>
	</div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.loader {
	width: 24px;
	height: 24px;
	display: block;
	border-radius: 999999px;
	border: 3px solid #55d56110;
	border-right-color: #55d561;
	animation: spin 500ms linear infinite;

	@keyframes spin {
		to {
			transform: rotate(1turn);
		}
	}
}
</style>
