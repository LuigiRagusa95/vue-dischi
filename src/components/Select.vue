<template>
	<label class="custom-select">
		<select>
			<option value="">All</option>
			<option value="Rock">Rock</option>
			<option value="Pop">Pop</option>
			<option value="Jazz">Jazz</option>
			<option value="Metal">Metal</option>
		</select>
	</label>
</template>

<script>
export default {
	name: "Select",
	data() {
		return {};
	},
	props: {
		options: Array,
	},
	methods: {},
	computed: {},
};
</script>

<style lang="scss" scoped></style>
