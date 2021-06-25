<template>
  <div>
    <SearchBar @termChange="onTermChange"></SearchBar>
    <VideoList></VideoList>
  </div>
</template>

<script>
import axios from 'axios';
import SearchBar from "./components/SearchBar";
import VideoList from "./components/VideoList";
export default {
  name: "App",
  components: {
    SearchBar,
    VideoList
  },
  methods: {
    onTermChange(serchTerm) {
        axios.get('https://www.googleapis.com/youtube/v3/search',{
            params:{
                key: process.env.VUE_APP_API_KEY,
                type: 'video',
                part: 'snippet',
                q: serchTerm
            }
        }).then(response => {
            console.log(response);
        })

        console.log(process.env.VUE_APP_API_KEY)
    },
  },
};
</script>
