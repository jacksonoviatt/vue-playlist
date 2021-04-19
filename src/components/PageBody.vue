<template>
  <div>
    <h1>Music Library</h1>
    <section>
      
      <article>
        <h3>Your playlist</h3>
        <!-- run a for loop through the musicLibrary Array -->
        <!-- bind songObject from the songlist to song from the for loop -->
        <play-list
         v-for="song in musicLibrary"
          :key="song.id"
          :songObject="song"
      ></play-list>
      </article>
      
      <article>
        <h3>Choose some songs</h3>
        <!-- run a for loop through the musicLibrary Array -->
       <!-- on the custom eventlistener songHasBeenClicked, run the function handle click status-->
        <!-- bind songObject from the songlist component to song from the for loop -->
        <song-list
          v-for="song in musicLibrary"
          :key="song.id"       
          @songHasBeenClicked="handleClickStatus"  
          :songObject="song"          
        ></song-list>
      </article>

    </section>
  </div>
</template>

<script>
import PlayList from "./PlayList.vue";
import SongList from "./SongList.vue";
export default {
  name: "page-body",
  components: {
    SongList,
    PlayList,
  },
methods: {
  // when the custom event runs, it will change the status of isSongClicked to true
      handleClickStatus(data) {
          data.isSongClicked = !data.isSongClicked;
          console.log(data.title);
          console.log(data.isSongClicked);

      }
  },

  data() {
    return {
//  array of songs
// is clicked is always default set as false
      musicLibrary: [
        {
          id: 1,
          title: "The Man in Me",
          artist: "Bob Dylan",
          isSongClicked: false,
        },
        {
          id: 2,
          title: "Spaceman",
          artist: "Harry Nilsson",
          isSongClicked: false,
        },
        {
          id: 3,
          title: "Supersonic Rocket Ship",
          artist: "The Kinks",
          isSongClicked: false,
        },
        {
          id: 4,
          title: "Brand New Key",
          artist: "Melanie Safka",
          isSongClicked: false,
        },
        {
          id: 5,
          title: "In the Summertime",
          artist: "Mungojerry",
          isSongClicked: false,
        },
        {
          id: 6,
          title: "Come and Get your Love",
          artist: "Redbone",
          isSongClicked: false,
        },
        {
          id: 7,
          title: "Jackie and Wilson",
          artist: "Hozier",
          isSongClicked: false,
        },
        {
          id: 8,
          title: "Australia",
          artist: "The Shins",
          isSongClicked: false,
        },
      ],
    };
  },
};
</script>

<style scoped>
section {
  display: grid;
  justify-items: center;
  grid-template-columns: 1fr 1fr;
}
</style>


