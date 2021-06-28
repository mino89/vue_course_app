<template>
  <div>
    <VideoListItem v-for="video in videos" :key="video.id.videoId"></VideoListItem>
  </div>
</template>

<script>
import VideoListItem from './VideoListItem'
export default {
    name: 'VideoList',
    components:{
        VideoListItem
    },
    props: ['videos']
    
}
</script>

<style>
</style>