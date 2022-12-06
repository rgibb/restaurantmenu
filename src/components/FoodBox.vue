<template>
    <div class="foodbox">


        

        <div v-for="food in foods" :key="food.id" >
            <FoodItem :food="food"/>
        </div>

    </div>
    


</template>'

<script>

    import FoodItem from './FoodItem.vue'


    export default{
        name: 'BookBox',
        components: {
            FoodItem
        },
        props:{
            
            foods: Array
        }
    }

</script>

<style scoped>

.bookbox{

background-color: tan;
padding: 1em;
color: gray;
}

</style>