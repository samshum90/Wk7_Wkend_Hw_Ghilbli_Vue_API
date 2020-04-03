<template>
  <div v-if="film" class="list-item">
      <h2>{{film.title}}</h2>
        <ghibli-film-image :title="film.title"> </ghibli-film-image>
      <p>Director:{{film.director}}</p>
      <p>Producer:{{film.producer}}</p>
      <p>Release Date:{{film.release_date}}</p>
      <p>Description:{{film.description}}</p>
  </div>
</template>

<script>
import {eventBus} from '../main.js'
import GhibliFilmImage from '@/components/GhibliFilmImage.vue'


export default {
    name: 'ghibli-film-detail',
    props: ['film'],
    components: {
        "ghibli-film-image": GhibliFilmImage
    },
    data(){
        return{
        }
    },


}
</script>

<style>
.list-item{
    border: solid 1px var(--yellowgrey);
    border-radius: 20px;
    width: 100%;

    padding: 0px 20px;
    background-color: var(--yellow);
    color: var(--darkgreen);
    margin:25px;
}
img{
  width: 100%;
  height: auto;
  object-fit: cover;
}
</style>