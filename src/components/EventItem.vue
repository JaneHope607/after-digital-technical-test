<template lang="html">
		<div class="event">
			<event-image class="event-image" :imageUrl="event.images.original"></event-image>
			<h2 class="event-title" v-html="event.title"></h2>
				<p class="event-date">{{ formatDateTime(event.instances[0].date_time) }}</p>
				<div class="event-description" v-html="event.short_description"></div>
			<div class="event-button-container">
				<button class="book-button" v-on:click="">Book now</button>
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

// function init() {
  
//   var i = 0;
//   var items = document.querySelectorAll(".event-details");
//   var itemsHeight = [];  

//   for (i = 0; i < items.length; i++) {
//     itemsHeight.push(items[i].offsetHeight);
//   }
  
//   var maxHeight = Math.max(...itemsHeight);

//   for (i = 0; i < items.length; i++) {
//     items[i].style.height = maxHeight + "px";
//   }
// }

// init();

</script>

<style lang="scss" scoped>
@import '@/assets/styles/variables.scss';
.event {
	flex-basis: 32%;
	background-color: $white;
	margin-bottom: 4%;
	box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
	align-items: center;

	h2, p, div {
		padding: 0 20px;
	}

	@media (max-width: $desktop-width) {
      flex-basis: 48%;
 	}

	@media (max-width: $tablet-width) {
      flex-basis: 90%;
 	}
}

.event-image {
	height: 250px;
	object-fit: cover;
	width: 100%;
}

.event-title {
	min-height: 80px;
}

.event-date {
	font-weight: bold;
}

.event-description {
	text-align: justify;
	min-height: 180px;
}

.event-button-container {
	text-align: center;
}
.book-button {
		background-color: $button-blue;
		height: 60px;
		width: 95%;
		text-align: center;
		color: $white;
		font-weight: bold;
		border-radius: 3px;
		border: none;
		font-size: 1rem;
		margin-bottom: 20px;
}

	.book-button:hover {
		cursor: pointer;
		background-color: $button-hover-blue;
	}

</style>