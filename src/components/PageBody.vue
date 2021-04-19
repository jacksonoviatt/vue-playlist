<template>
  <div>
    <h1>Music Library</h1>
    <section>
      <article>
        <h3>Your playlist</h3>
        <play-list
         v-for="song in musicLibrary"
          :key="song.id"
          :songObject="song"
      ></play-list>
      </article>
      
      <article>
        <h3>Choose some songs</h3>
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
      handleClickStatus(data) {
        document.body.style.color = "red";
         
          // console.log(this.songObject);
          data.isSongClicked = !data.isSongClicked;
          console.log(data.title);
          console.log(data.isSongClicked);

      }
  },

  data() {
    return {
      // songClicked: false,
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


