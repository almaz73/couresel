<template>
    <div class='box'> 
        <br>       
        <img class="box-img" src="./assets/picture/1.png"/>
        <div class='title'>{{title}}</div>
        <div class='cost'>{{cost}} руб.
            <button></button>
        </div>
    </div>
</template>
<script>
  export default{
    name:'Box',
    props: {
      title: {
        type: String
      },
      cost:{
          type: Number
      },
      pic:{
          type: String
      },

    },
    computed:{
        src2: function (){
            let Q = "/dist/"+this.pic
            return "./assets/1.png";
            /*return Q*/
            /*return "./assets/1.png";*/
            /*return "./assets/"+pic;*/
        }
    }


    
  }
</script>
<style>
    .box-img{
        width: 80px;
        min-width: 80px;
        overflow: hidden;
    }
    .box{
        position: relative;
        width: 140px;
        height: 250px;
        /*border: 1px solid red;*/
        background: white;
    }
    .cost{
        position: absolute;
        bottom: 10px;
        font-weight: bold;
        font-size: 12px;
        margin: 0 auto;
        width: 140px;
    }
    .cost button{
        padding: 0;
        width: 27px;
        height: 27px;
        border: 0;
        cursor: pointer;
        background-image: url("./assets/picture/basket.png");        
    }
    .title{
        position: absolute;
        top: 160px;
        font-size: 14px;
        color: #3c8dcb;
    }
</style>
