<template>
	<div class="card">
		<div class="card-image">
			<img :src="poster" alt="poster-image" />
		</div>
		<div class="card-info">
			<div class="card-info-title">
				<h4>{{ title }}</h4>
			</div>
			<span class="card-info-author">{{ author }}</span>
			<span class="card-info-year">{{ year }}</span>
			<span class="card-info-genre">{{ genre }}</span>
		</div>
	</div>
</template>

<script>
export default {
	name: "Card",
	props: {
		poster: String,
		title: String,
		author: String,
		genre: String,
		year: String,
	},
};
</script>

<style lang="scss" scoped>
.card {
	display: flex;
	padding: 1rem;
	margin: 0.5rem;
	flex-flow: column;
	cursor: pointer;
	border-radius: 3px;
	transition: 0.2s ease;
	width: calc((100% / 6) - 1rem);
	background: rgba($color: #ffffff, $alpha: 0.05);
	box-shadow: 0 2px 8px rgba($color: #000000, $alpha: 0.2);

	&:hover {
		background: rgba($color: #ffffff, $alpha: 0.1);
	}

	&-image {
		width: 100%;
		display: flex;
		overflow: hidden;
		position: relative;
		padding-bottom: calc(100% * 1);

		> img {
			top: 0;
			left: 0;
			width: 100%;
			position: absolute;
			object-fit: contain;
		}
	}

	&-info {
		display: flex;
		margin-top: 1rem;
		text-align: center;
		flex-direction: column;

		&-title {
			width: 100%;
			display: flex;
			min-width: 0;
			justify-content: center;

			> h4 {
				overflow: hidden;
				color: #f5f5f5;
				font-size: 1.25rem;
				line-height: 2.5rem;
				white-space: nowrap;
				text-overflow: ellipsis;
			}
		}

		&-author,
		&-year,
		&-genre {
			font-size: 0.875rem;
			color: #ffffff40;
			line-height: 1.5rem;
		}

		&-genre {
			color: #ffffff;
			font-size: 1rem;
		}
	}
}
</style>
