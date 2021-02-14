<template>
  <Options :options="videos" :link="changeLink" />
  <VideoStream :link="selected"/>
</template>

<script>
import Options from "./components/Options.vue"
import VideoStream from "./components/VideoStream.vue"
import axios from "axios"

export default {
  name: 'App',
  components: {
    VideoStream,
    Options
  },
  data(){
    return {
      videos: [],
      selected: ''
    }
  },
  mounted: function(){
    this.allVideos();
  },
  methods: {
    async allVideos(){
      let res = await axios.get('http://localhost:2828/allvideos')
      this.videos = res.data.videos;
    },
    changeLink(url){
      this.selected = url;
    }
  }
}
</script>
