<template>
  <div id>
    <SearchBar @termChange="onTermChange"> </SearchBar>
  </div>
</template>

<script>
import SearchBar from './components/SearchBar';
const API_KEY = 'AIzaSyD6mCviaBBfaEdQ-w90Tl83M2KYHXNg6Wg'

export default {
  name: 'App',
  components: {
    SearchBar
  },
  methods: {
    onTermChange(searchTerm) {
      console.log(searchTerm)
    }
  }

}
</script>