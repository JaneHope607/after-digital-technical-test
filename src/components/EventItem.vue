<template lang="html">
	<div class="event">
		<div class="event-image">
			<event-image :imageUrl="event.images.cta"></event-image>
		</div>
		<div class="details">
			<h2 class="event-title" v-html="event.title"></h2>
			<p class="event-date">{{ formatDateTime(event.instances[0].date_time) }}</p>
			<div class="event-description" v-html="event.short_description"></div>
		</div>
		<div class="book-button">
			<button v-on:click="">Book now</button>
		</div>
	</div>
</template>

<script>
import moment from 'moment'
import EventImage from '@/components/EventImage.vue'
 
export default {
	name: 'event-item',
	props: ['event'],
	components: {
		'event-image': EventImage
	},
	
	methods: {
		formatDateTime(value) {
			return moment(value).format("h:mm a | DD MMM YYYY");
		}
	},
};

</script>

<style lang="scss" scoped>
@import '@/assets/styles/variables.scss';
.event {
	flex-basis: 32%;
	background-color: $white;
	margin-bottom: 2%;
}

.event-image {
	height: 250px;

	img {
	object-fit: cover;
	width: 100%;
	height: 100%;
	}
}

.details {
	margin: 20px;
}

.event-title, .event-date {
	font-weight: bold;
}

.event-description {
	text-align: justify;
}

.book-button { 
	text-align: center;

	button {
		background-color: $button-blue;
		align-items: center;
		height: 60px;
		width: 80%;
		text-align: center;
		color: $white;
		font-weight: bold;
		border-radius: 3px;
		border: none;
	}
}

</style>