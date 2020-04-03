<template>
    <img :src="imageName">
</template>

<script>
import noImage from '@/assets/noimgfnd.jpg'

export default {
    name: 'ghibli-film-image',
    props:['title'],
    computed: {
        imageName() {
            const image = require("@/assets/" + this.title + ".jpg");
            return image != undefined ? image : noImage;
        }
    }
}
</script>

<style>

</style>