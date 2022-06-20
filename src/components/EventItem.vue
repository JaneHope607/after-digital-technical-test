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

function init() {
  
  var i = 0;
  var items = document.querySelectorAll(".details");
  var itemsHeight = [];  

  for (i = 0; i < items.length; i++) {
    itemsHeight.push(items[i].offsetHeight);
  }
  
  var maxHeight = Math.max(...itemsHeight);

  for (i = 0; i < items.length; i++) {
    items[i].style.height = maxHeight + "px";
  }
}

init();

</script>

<style lang="scss" scoped>
@import '@/assets/styles/variables.scss';
.event {
	flex-basis: 32%;
	background-color: $white;
	margin-bottom: 4%;
	box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
	position: relative; 

	@media (max-width: $desktop-width) {
      flex-basis: 48%;
 	}

	@media (max-width: $tablet-width) {
      flex-basis: 90%;
 	}
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

.event-title {
	min-height: 110px;

	.event-date {
		font-weight: bold;
	}
}

.event-description {
	text-align: justify;
	min-height: 250px;
}

.book-button { 
	text-align: center;
    position: absolute;
	bottom: 20px;
	width: 100%;

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