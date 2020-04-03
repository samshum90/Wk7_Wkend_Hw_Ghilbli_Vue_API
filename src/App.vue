<template>
  <div class="main-container">
    <ghibli-header title="Studio Ghibli" />
    <ghibli-header v-if="!films.length" title="LOADING..." />
    <div class="list-info" v-if="films.length">
      <ghibli-film-list 
        :films="films">
      </ghibli-film-list>
      <ghibli-film-detail
       v-if="selectedFilm"
        :film="selectedFilm">
      </ghibli-film-detail>
    </div>
    <!-- <ghible-watched-list :watched="watched"></ghible-watched-list> -->
  </div>
</template>

<script>
import { eventBus } from '@/main.js';
import GhibliFilmList from "@/components/GhibliFilmList.vue";
import GhibliFilmDetail from "@/components/GhibliFilmDetail.vue";
import GhibliHeader from "@/components/GhibliHeader.vue";

export default {
  name:'app',
  data() {
    return{
      films: [],
      selectedFilm: null
    }
  },
  mounted(){
    fetch('https://ghibliapi.herokuapp.com/films')
    .then(response => response.json())
    .then(json => this.films = json)

    eventBus.$on('film-selected', (film) => {
      this.selectedFilm = film
      })
  },
  components: {
    "ghibli-film-list": GhibliFilmList,
    "ghibli-film-detail": GhibliFilmDetail,
    "ghibli-header": GhibliHeader
  }
}
</script>

<style>
*{
  font-family: Meiryo, "Yu Gothic", YuGothic, Helvetica, sans-serif;
}
html{
  background-color: var(--darkblue);

}
:root{
--darkgreen: #002627;
--greengrey: #556a5b;
--yellowgrey: #6e6046;
--pink: #deacab;
--white: #f5f1e6;
--yellow: #ffea81;
--peach: #fbe5b3;
--greenwhite: #dce4cf;
--lightblue: #36b3df;
--darkblue: #0598ce;
}

.main-container{
  color: var(--white);
  padding: 30px;
}

.list-info{
  display: flex;
  width: 100%;
  background-color: var(--lightblue);
  border-radius: 10px;
}
</style>