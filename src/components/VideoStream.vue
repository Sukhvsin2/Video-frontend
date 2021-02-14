<template>
  <div v-if="link != ''" class="videoComponent">
    <h2>Video Stream</h2>
    <video :key="link" id="videoPlayer" width="650" controls autoplay='false'>
        <source :src="link" type="video/mp4" />
    </video>
  </div>
</template>

<script>
export default {
    name: 'VideoStream',
    props: {
        link: String
    },
    data(){
        return{
            urlUse : ''
        }
    },

}
</script>

<style>

</style>