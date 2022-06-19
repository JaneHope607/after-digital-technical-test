<template>
  <app-header />
  <router-view/>
  <event-list />
  <event-item :eventsData="events" />
</template>

<script>

import AppHeader from "@/components/AppHeader.vue";
import EventItem from "@/components/EventItem.vue";
import EventList from "@/components/EventList.vue"

import eventsData from "@/events.json";
let events = eventsData.data.getEvents

export default {
  components: {
    'app-header': AppHeader,
    'event-list': EventList,
    'event-item': EventItem
  },

  data () {
    return {
      events: events
    };
  },

  // data () {
  //   return {
  //     events: []
  //   }
  // },

  // // calling API
  // methods: {
  //   fetchData(){
  //     fetch("https://t-bridge.s3.eu-west-1.amazonaws.com/events.json")
  //       .then(response => response.json())
  //       .then(events => this.events = events);
  //   }
  // },
  // mounted() {
  //   this.fetchData();
  //   eventBus.$on("refresh-data", this.fetchData);
  // },

  // components: {
  //   'event-list': EventList
  // }
};

</script>

<style lang="scss">
@import "@/assets/styles/variables.scss";

* {
    box-sizing: border-box;
}

body {
  background-color: $main-background-colour;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif; 
  font-size: 18px;
  margin-top: 10px;
  color: $black;

  @media (max-width: $mobile-width) {
      font-size: 14px;
  }
}


</style>
