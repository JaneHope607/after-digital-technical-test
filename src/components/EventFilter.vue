<template lang="html">
    <div class="event-search">
        <h1>Search events</h1>
        <div class="event-searchbar">
            <form>
                <label class="event-search-label" for="keyword">Keywords</label>
                <input class="event-search-input" id="keyword" type="text" v-model="searchTerm" placeholder="Enter search terms here" v-on:keyup="onChange" />
            </form>
        </div>
    </div>

</template>

<script>

export default {
    data() {
        return {
            'searchTerm': ''
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
    padding: 0 80px;

    @media (max-width: $desktop-width) {
        padding: 0 60px
 	}

	@media (max-width: $tablet-width) {
        padding: 0 20px;
 	}

    .event-searchbar {
        background-color: $white;

        form {
            padding: 30px 0;
            display: flex;
            flex-wrap: wrap;
            align-items: center;

            .event-search-label {
                margin: 0 20px;
                font-weight: 600;
                font-size: 1.4rem;
            }
            .event-search-input {
                font-size: 1rem;
                width: 95%;
                height: 60px;
                border: 2px solid $main-background-colour;
                padding: 10px 50px 10px 15px;
                margin: 20px;
                border-radius: 3px;
                background-image: url('@/assets/search.png');
                background-repeat: no-repeat;
                background-position: 98% center;
                background-size: 30px;
                flex-grow: 1;
            }

            input[type="text"]:focus {
                outline : none;
            }
        }  
    }
}

</style>