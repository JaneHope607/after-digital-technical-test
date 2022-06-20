<template lang="html">
    <div class="event-filter">
        <input type="text" v-model="searchTerm" placeholder="Enter search terms here" v-on:keyup="onChange" />
        <div class="item fruit" v-for="event in events" :key="event">
            <p>{{ event.title }}</p>
        </div>
        <!-- <div class="item error" v-if="input&&!filteredList().length">
            <p>No results found!</p>
        </div> -->
    </div>
</template>

<script>

export default {
    data() {
        return {
            "searchTerm": ''
        };
    },
    name: 'event-filter',
    props: ['events'],
    // methods: {
    //     filteredEvents () {
    //     let foundEvent = this.events.find((event) => {
    //     return event.title.toLowerCase().indexOf(this.search.toLowerCase()) > -1
    //   })


    //   this.selectedEvent = foundEvent
    //   this.$emit('event-selected', this.foundEvent)
    //         // return this.events.filter((event) => event.title.toLowerCase().includes(this.searchTerm));
    //     }
    // },

    methods: {
        onChange() {
            this.$emit("search", this.searchTerm)
        }
    }

    // methods: {
    //     updateFilter(value) {
    //         this.$emit('update-filter' , this.search)
    //     }
    // }
}

</script>

<style lang="scss">
</style>