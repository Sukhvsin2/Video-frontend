<template>
  <h1>Video Stream</h1>
  <video id="videoPlayer" width="650" controls autoplay='true'>
      <source src="http://localhost:2828/video" type="video/mp4" />
  </video>
</template>

<script>
import axios from "axios"
export default {
    name: 'VideoStream',
    data(){
        return{
            urlUse : ''
        }
    },
    created: function(){
        this.apiCall();
    },
    methods:{
        apiCall: async () => {
            try {
                let res = await axios.get('http://localhost:2828/video')
                console.log('check res ', res);
                this.urlUse = res.data;
            } catch (error) {
                console.log(error);
            }
        }
    }

}
</script>

<style>

</style>