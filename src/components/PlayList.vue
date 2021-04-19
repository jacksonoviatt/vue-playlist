<template>
   <div @click="songObject.isSongClicked = !songObject.isSongClicked" v-if="songObject.isSongClicked">
   <h3>{{songObject.title}}</h3>
      <p>by {{ songObject.artist}}</p> 
  </div>
</template>

<script>
    export default {
        name: "play-list",
         props: {
        songObject: Object,
  },
    }
</script>

<style scoped>

</style>