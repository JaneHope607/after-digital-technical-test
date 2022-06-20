<template>
  <app-header />
  <router-view/>
  <!-- <event-filter :events="events"/> -->
  <event-filter @search="getFilteredEvents($event)"/>
  <event-list :events="filteredEvents"/>
</template>

<script>

import AppHeader from '@/components/AppHeader.vue'
import EventFilter from '@/components/EventFilter.vue'
import EventList from '@/components/EventList.vue'

import eventsData from '@/events.json';
import { EventEmitter } from 'events';

// let events = eventsData.data.getEvents

export default {
  name: 'app',
  components: {
    'app-header': AppHeader,
    'event-list': EventList,
    'event-filter': EventFilter
  },

  data () {
    return {
      events: eventsData.data.getEvents,
      filteredEvents : eventsData.data.getEvents
    }
  },

  methods: {
    getFilteredEvents(search) {
     this.filteredEvents = this.events.filter(event => event.title.toLowerCase().includes(search.toLowerCase()))
    }
  }
};

</script>

<style lang="scss">
@import "@/assets/styles/variables.scss";

* {
    box-sizing: border-box;
}

body {
  background-color: $main-background-colour;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  font-size: 18px;
  margin-top: 10px;
  color: $black;

  @media (max-width: $mobile-width) {
      font-size: 14px;
  }
}

h1 {
  font-size: 2.5rem;
}


</style>
