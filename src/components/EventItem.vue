<template lang="html">
	<div class="event">
		<div class="event__inner-wrapper">
			<div class="event-image">
				<event-image></event-image>
			</div>
			<div class="details">
				<h2 v-html="event.title"></h2>
				<p>{{ formatDateTime(event.instances[0].date_time) }}</p>
				<div class="event-description" v-html="event.short_description"></div>
			</div>
		</div>
	</div>
</template>

<script>
import moment from 'moment'
import EventImage from "@/components/EventImage.vue"
 
export default {
	name: "event-item",
	props: ["event"],
	components: {
		"event-image": EventImage
	},
	
	methods: {
		formatDateTime(value) {
			return moment(value).format("h:mm a | DD MMM YYYY");
		}
	}
};

</script>

<style lang="scss" scoped>

</style>