<template>
    <div class='box'>
        <div class="div-img">
            <img class="box-img" :src="src"/>
        </div>            
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
      title: {type: String},
      cost:{type: Number},
      pic:{type: String},
      slides:{type: Array},
    },
    computed:{
        src: function (){
            let text = '';
            [0,1,2,3,4,5].map(el =>{
                 if (this.slides[el+2].pic==this.pic) text =  "./picture/"+this.pic;                                    
            });
            return text;
        }
    }    
  }
</script>
<style>
    .div-img{
        min-height: 140px;
        padding-top: 20px;
        overflow: hidden;
    }
    .box{
        position: relative;
        width:100%;
        height: 250px;
        background: white;                
    }
    .box-img{
        width: 80px;
        line-height: 140px;
    }
    .cost{
        position: absolute;
        bottom: 10px;
        font-weight: bold;
        font-size: 12px;
        margin: 0 auto;
        width: 100%;
    }
    .cost button{
        padding: 10px;
        margin-left:20px;
        width: 27px;
        height: 27px;
        border: 0;
        cursor: pointer;
        background-image: url("/picture/basket.png");        
    }
    .title{
        margin-bottom: 60px;
        font-size: 14px;
        color: #3c8dcb;
    }
</style>
