<template>
    <div class="header">
        <h1>Popular TV Shows</h1>
    </div>
</template>

<script>
export default {
    //name our component for export so this template can be called upon
    name: "Header"

}
</script>
    
<style scoped>
/* scoped allows this style to onbly apply to this component*/
    .header
    {
        background: #333;
        color:white;
        text-align: center;
        padding:10px;
        margin:0px;
        font-size: 25px;
    }

</style>