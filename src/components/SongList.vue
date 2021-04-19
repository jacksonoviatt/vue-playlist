<template>
<!-- on click function changeLists will run and emit the songObject to the pageBody
 revert back to false 
this component will only show if isSongClicked is false -->
 
  <div @click="changeLists()" v-if="!songObject.isSongClicked">
      <h3>{{songObject.title}}</h3>
      <p>by {{ songObject.artist}}</p> 
  </div>
</template>

<script>
export default {
  name: "song-list",
  // set the property of songObject to know that it will take in an object
  props: {
    songObject: Object,
  },
  
methods: {
  // this function broadcasts information to the parent function
  // and sets songHasBeenClicked to a custom event listener
            changeLists: function () {
                this.$emit("songHasBeenClicked", this.songObject);
            }
        },
};
</script>

<style scoped>
</style>