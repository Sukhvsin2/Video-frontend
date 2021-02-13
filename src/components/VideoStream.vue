<template>
  <h1>Video Stream</h1>
  <video id="videoPlayer" width="650" controls muted="muted" autoplay>
      <source src="http://localhost:2828/video" type="video/mp4" />
  </video>
</template>

<script>
export default {
    name: 'VideoStream',
    mounted(){
        this.apiCall();
    },
    methods:{
        apiCall: async () => {
            const headers = {
                "Content-Range": 'bytes 0'
            }
            try {
                var res = await fetch('http://localhost:2828/video', headers)
                console.log(await res.json());
            } catch (error) {
                console.log(error);
            }
        }
    }

}
</script>

<style>

</style>