<template lang="html">
	<div class="events-wrapper" v-if="events.length">
        <event-item
            v-for="(event, index) in events"
            :event="event"
            :key="index">
        </event-item>
	</div>
</template>

<script>

import EventItem from '@/components/EventItem';

export default {
    name: 'event-list',
    props: ['events'],
    components: {
        'event-item': EventItem
    }
};

</script>

<style lang="scss" scoped>
@import '@/assets/styles/variables.scss';

.events-wrapper {
    display: flex;
    flex-wrap: wrap;
    justify-content:space-around;
    flex-direction: row;
    width: 100%;
    padding: 80px;

    @media (max-width: $desktop-width) {
        padding: 60px
 	}

	@media (max-width: $tablet-width) {
        padding: 20px;
 	}
}

</style>