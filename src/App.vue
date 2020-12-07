<template>
  <div id="app">
    <Header/>
    <div class="card-group">
      <TvShows v-for="tvshows in shows" :key="tvshows.id" v-bind:tvshows="tvshows" v-bind:title="tvshows.name" v-bind:overview="tvshows.overview" v-bind:poster="url+tvshows.poster_path"/>
    </div>
  </div>
</template>

<script>
//import our components and templates
import Header from './components/Header.vue';
import TvShows from './components/TvShows.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    Header,
    TvShows
  },
  data()
  {
    return{
      shows: ""
    }
  },
  mounted()
  {
    //get axios call for most popular tv shows and assign them to our "shows object"
    axios.get("https://api.themoviedb.org/3/tv/popular?api_key=7ba521321ecd56ec9ebe9f7b0b16ef0d&language=en-US&page=1")
    .then( (response) => {
      this.shows = response.data.results.slice(0,4);
      //loops through our axios results and logs the name of each object that was received
      for(var i = 0; i < this.shows.length; i++)
      {
        console.log(this.shows[i].name);
      }
    })
    //this.url allows us to access the iamges off of our axios poster_path call
    this.url = "https://image.tmdb.org/t/p/w500";
  }
}
</script>

<style>
  
</style>
