<template>
  <div class="listitem">
      <p v-on:click="handleClick">{{film.title}}</p>
  </div>
</template>

<script>
import {eventBus} from "@/main.js";

export default {
    name:"List-Item",
    props:['film'],
    methods: {
        handleClick(){
            eventBus.$emit('film-selected', this.film)
        }
    }
}
</script>

<style>
    .listitem{
        font-size: 1.5em;
    }
</style>