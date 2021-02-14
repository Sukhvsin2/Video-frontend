<template>
  <h1>
    Video Options
  </h1>
    <div v-for="vid in options" :key="vid">
      <button class="optionButton" @click="setLink(vid)" >{{vid}}</button>
    </div>
</template>

<script>
export default {
  name: 'Video Streaming',
  props: {
    options: Array,
    link: Function,
  },
  methods: {
    setLink(vid){
      this.link(`http://localhost:2828/videos/${vid}`);
    }
  }
}
</script>

<style scoped>
.optionButton{
  margin: 10px;
  width: 15vw;
  padding: 5px;
  cursor: pointer;
  overflow: hidden;
}
</style>
