<template>
  <div class="container">
    <HeaderTop websiteName="Restaurant Menu" authorName="Ryan Gibbons" />

    <FoodBox :foods="foods" />
    

</div>
</template>

<script>

import HeaderTop from './components/HeaderTop.vue'
import FoodBox from './components/FoodBox.vue'

export default {
  name: 'App',
  components: {    
    HeaderTop,
    FoodBox, 
  },

  data(){
    return {
      foods: []
    }

  },

  methods: {

    // promises

      async fetchFoods(){
          const res = await fetch('restaurant-menu-f556e5.netlify.app/.netlify/functions/foods')
          const data = await res.json()
          console.log( data )
          return data
      }


  },
  async created(){
    this.foods = await this.fetchFoods()
  }
}

</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Montserrat', sans-serif;
}
.container {
  max-width: auto;
  background: rgb(108, 124, 140);
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 0.3em solid black;
  padding: 30px;
  border-radius: 5px;
}

div{
  margin-bottom: 0.5em;
}
@media only screen and (max-width:500px){
    .container{
      max-width: 400px;
      background: lightslategray;
      margin: 30px auto;
      overflow: auto;
      min-height: 300px;
      border: 0.3em solid black;
      padding: 30px;
      border-radius: 5px;
        
    }
  }

</style>
