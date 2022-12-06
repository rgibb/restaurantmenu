<template>

    <div :class="food.published ? 'grey': 'black' ">
        <div class="foodBox">
            <div id="text">
        <div id="type">{{food.type}}</div>
        <div id="food">{{food.food}}</div>
        <div id ="sides">{{food.sides}}</div>
        <div id="price">${{food.price}}</div>
        <div id="cals">{{food.calories}}</div>
            </div>
        <div id><img id = "image" v-bind:src="food.image"></div>
    </div>
    </div>

</template>

<script>


export default{
    name: 'FoodItem',
    props:{
        food: Array
    }
}


</script>

<style scoped>

#type{
    font-family: 'Abril Fatface';
    font-weight: bold;
    font-size: 2em;
}
#food{
    margin: 2px;
    padding-left: 3em;
}
#sides{
    margin: 2px;
    padding-left: 3em;
}
#price{
    margin: 2px;
    padding-left: 3em;
}
#cals{
    margin: 2px;
    font-size: .6em;
    padding-left: 5em;
}
#image{
    width:auto;
    height:300px;
    padding-top: 2.5em;
}

div{
    background-color: rgb(183, 181, 181);
    color: black;
    padding: 1em;
}

.grey{
background-color: grey !important;

}
.black{
    color: black;
}

.foodBox{
        height: auto;
        display: grid;
        grid-template-columns: .5fr .10fr;
        grid-template-rows: 0.2 ;
        grid-template-areas: 
        "text image";
}
@media only screen and (max-width:500px){
    .foodBox{
        max-width: 400px;
        margin: 30px auto;
        overflow: auto;
        display: grid;
        grid-template-columns: 1fr;
        grid-template-rows: 0.4fr 0.25fr;
        grid-template-areas: 
        "text"
        "image";
        
    }
    #type{
    font-family: 'Abril Fatface';
    font-weight: bold;
    padding-left:1.5em;
    
}
#image{
    width:auto;
    height:250px;
    display:block;
    object-fit:contain;
    margin-left: auto;
    margin-right: auto;
}
  }


</style>