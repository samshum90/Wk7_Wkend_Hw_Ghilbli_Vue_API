<template>
    <div class="title">
       <img src="@/assets/totologo.png" alt="studio ghibli totoro logo"> <h1>{{ title }}</h1>
    </div>
</template>

<script>
export default {
    name:"ghibli-header",
    props:["title"]
}
</script>

<style>
.title{
    display: flex;
    font: bold 1em Futura;
    color: var(--yellow);
    background-color: var(--greengrey);
    border-radius: 10px;
    align-content: center;
    padding: 3px;
    margin-bottom: 20px;
} 
h1{
    margin-left: 20px;
}
.title img {
    height: 75px;
    width: auto;
    object-fit: cover;
    filter: saturate(0%) brightness(10000%);
    padding: 5px;
}
</style>