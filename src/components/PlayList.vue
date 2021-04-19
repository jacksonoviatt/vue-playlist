<template>
<!-- on click isSongClicked boolean will revert back to false -->
<!-- this component will only show if isSongClicked is true -->
  <div
    @click="songObject.isSongClicked = !songObject.isSongClicked"
    v-if="songObject.isSongClicked"
  >
    <h3>{{ songObject.title }}</h3>
    <p>by {{ songObject.artist }}</p>
  </div>
</template>

<script>
export default {
  name: "play-list",
  props: {
    // set the property of songObject to know that it will take in an object 
    // when the variable is updated in the other components, this component will receive the message
    songObject: Object,
  },
};
</script>

<style scoped>
</style>