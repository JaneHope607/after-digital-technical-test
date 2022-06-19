<template lang="html">
	<div id="events">
        <div class="event-wrapper" v-if="events.length">
            <event-item
                v-for="(event, index) in events"
                :event="event"
                :key="index">
            </event-item>
        </div>
	</div>
</template>

<script>

import EventItem from "@/components/EventItem";

export default {
    name: "event-list",
    props: ["events"],
    components: {
        "event-item": EventItem
    }
}

</script>

<style lang="scss" scoped>
</style>