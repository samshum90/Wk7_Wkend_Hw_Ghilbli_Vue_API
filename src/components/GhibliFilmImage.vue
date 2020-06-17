<template>
    <img :src="imageName" @error="imgError">
</template>

<script>
import noImage from '@/assets/noimgfnd.jpeg'

export default {
    name: 'ghibli-film-image',
    props:['title'],
    data(){
  return{
    defaultImg: ('require(@/assets/noimgfnd.jpeg')
  }
    },
    computed: {
        imageName() {
            const image = require("@/assets/" + this.title + ".jpg");
            return image != undefined ? image : noImage;
        }
    },
    methods:{
 imgError(){
  this.src = this.defaultImg;
 } 
}
}



</script>

<style>

</style>