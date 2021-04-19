<template>
  <div @click="changeLists()" :id="listId" v-if="!songObject.isSongClicked">
      <h3>{{songObject.title}}</h3>
      <p>by {{ songObject.artist}}</p> 
  </div>
</template>

<script>
export default {
  name: "song-list",
  props: {
    songObject: Object,
    // songClicked: Boolean,
  },
  
   
data() {
    return {
        listId: "songId-" + this.songObject.id
    }
},
methods: {
            changeLists: function () {
                this.$emit("songHasBeenClicked", this.songObject);
            }
        },
};
</script>

<style scoped>
</style>