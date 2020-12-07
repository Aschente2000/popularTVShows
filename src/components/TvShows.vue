
<template>
    <!-- Creating a bootstrap card to hold our show objects and display them all nice and neat -->
    <div class="card">
        <img v-bind:src="poster" class="card-img-top" alt="movie posters">
        <div class="card-body">
            <h5 class="card-title">{{title}}</h5>
            <p class="card-text">{{overview}}</p>
        </div>
    </div>

</template>

<script>
// set our props and the name of our component so that it can be exported and the props will receive data
export default {
    name: "TvShows",
    props:['tvshows','title','overview',"poster"]
}
</script>

<style scoped>
    
</style>

