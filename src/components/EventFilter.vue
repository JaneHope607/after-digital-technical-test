<template lang="html">
    <div class="event-search">
        <h1>Search events</h1>
        <div class="event-searchbar">
            <form>
                <label for="keyword">Keywords</label>
                <input id="keyword" type="text" v-model="searchTerm" placeholder="Enter search terms here" v-on:keyup="onChange" />
            </form>
        </div>
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
    methods: {
        onChange() {
            this.$emit("search", this.searchTerm)
        }
    }
}

</script>

<style lang="scss" scoped>
@import '@/assets/styles/variables.scss';

.event-search {
    margin: 0 80px;
    .event-searchbar {
        background-color: $white;

        form {
            text-align: center;
            padding: 30px 0;

            label {
                margin: 0;
            }

            input {
                width: 95%;
                height: 60px;
                border: 2px solid $main-background-colour;
                padding: 15px;
                margin: 15px;
            }
        }  
    }
}

</style>