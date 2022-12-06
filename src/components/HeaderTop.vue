<template>
    <div>
        <h1> {{websiteName}} </h1>
        <h4> {{authorName}} </h4>
    </div>
</template>
    
    <script>
    
    export default{
        name: 'HeaderTop',
        props:{
            websiteName: String,
            authorName:String
        }
    }
    
    </script>
    
    <style scoped>
    
    @import url('https://fonts.googleapis.com/css?family=Actor');
    * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    }
    div{
        text-align: center;
        font-family: 'Actor';
    }

    h1{
        font-size: 3.5em;
        font-weight: bold;
        
    }
    h4{ 
        font-size: .8em;
    }
    
    </style>