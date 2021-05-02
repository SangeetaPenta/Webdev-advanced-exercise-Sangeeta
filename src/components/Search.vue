<template>
  <div>
    <h2>Search Bar</h2>
    <input v-model="searchResult"  type="text"/>
    <button type="button" @click="getSearchResults()">
        Search
    </button>
    <search-results :results="searchData"></search-results>
  </div>
</template>

<script>
import axios from "axios"
import SearchResults from './SearchResults.vue'
export default {
  components: { SearchResults },
    name: 'Search',
    data () {
        return {
            searchResult: 'statista',
            searchData: [],
            // isclick: false
        }
    },
    methods: {
        getSearchResults() {
            if(this.searchResult === 'statista') {
                // console.log('get the results')
                axios.get("https://cdn.statcdn.com/static/application/search_results.json")
                .then((responce) => {
                    // console.log(responce.data.items)
                    this.searchData = responce.data.items

                })
            }else {
                this.searchData = []
            }
        }
    }
}
</script>

<style>
input {
    width: 100%;
    max-width: 400px;
    padding: 5px;
    margin: auto;
}
button {
    padding: 5px;    
}
</style>