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
	}
};

</script>

<style lang="scss" scoped>
@import '@/assets/styles/variables';
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
	display: flex;
	flex-wrap: wrap;
}

.event-title, .event-date {
	font-weight: bold;
}

.event-description {
	text-align: justify;
}

</style>