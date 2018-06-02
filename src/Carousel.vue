<template>
  <div class='carousel' >
<div class="carousel-head">
    <hr/>
    <div class="text1">ЛУЧШИЕ ЖИДКОСТИ</div>
    <div class="text2">ПОКАЗАТЬ ВСЕ</div>
</div>
    <div class='carousel-view'>
      <div class='carousel-controls' @click="previous"> &#706; </div>
      <transition-group
        class='carousel-transaction'
        tag="div">
      
        <div
          v-for="slide in slides" 
          class='slide'
          :key="slide.id">
          <Box :title='slide.title' :cost='slide.cost' :pic='slide.pic'   />
          
        </div>
      
      </transition-group>
      <div class='carousel-controls' @click="next">></div>

    </div>
  </div>
</template>

<script>

import Box from './Box.vue';

export default {
  name: 'carousel',
  components: {
    Box
  },

  data () {
    return {
      slides: [
        {
          title: 'Жидкость Candy King "Batch"',
          pic: '1.png',
          cost: 1290,
          id: 1
        },
        {
          title: 'Жидкость ATLAS "Cuba Toronto"',
          pic: '2.png',
          cost: 300,
          id: 2
        },
        {
          title: 'Жидкость Charlies Chalk "Slam Berry"',
          pic: '3.png',
          cost: 1390,
          id: 3
        },
        {
          title: 'Жидкость Candy King "Batch 2"',
          pic: '4.png',
          cost: 249,
          id: 4
        },
        {
          title: 'Жидкость ATLAS "Cuba Toronto"',
          pic: '5.png',
          cost: 350,
          id: 5
        },
        {
          title: 'Жидкость Candy King "Batch 3"',
          pic: '6.png',
          cost: 2000,
          id: 6
        },
        {
          title: 'Жидкость Charlies Chalk "Slam Berry 2"',
          pic: '7.png',
          cost: 500,
          id: 7
        },
        {
          title: 'Жидкость ATLAS "Cuba Toronto"',
          pic: '8.png',
          cost: 300,
          id: 8
        },
        {
          title: 'Жидкость Candy King "Batch 4"',
          pic: '9.png',
          cost: 300,
          id: 9
        },
        {
          title: 'Жидкость Candy King "Batch 5"',
          pic: '10.png',
          cost: 300,
          id: 10
        }
      ]
    }
  },

  methods: {
    next () {
      const first = this.slides.shift()
      this.slides = this.slides.concat(first)
    },
    previous () {
      const last = this.slides.pop()
      this.slides = [last].concat(this.slides)
    }
  }
}
</script>

<style >
.carousel{
  background: #f5f5f5;
  text-align: center;
  margin-top:50px;
  width: 730px;
  margin: 0 auto;
  padding-bottom: 30px;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif; 
}

.carousel-head {
    position: relative;
    padding-top: 10px;       
    margin: 20px;    
}
.text1 {
    position: absolute;
    left: 230px;
    top: 6px;
    background: #f5f5f5;
    padding: 0 10px;
    font-size: 20px;
    font-weight: bold;
}
.text2 {
    position: absolute;
    right: -12px;
    top: 12px;
    background: #f5f5f5;
    padding: 0 10px;
    font-size: 10px;
}

.carousel-view {  
  width:700px;
  margin: 0 auto;
}

.carousel-controls{
  display: inline-block;
  line-height: 150px;
  font-family:monospace, 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
 /* background: #ddd;*/
  width: 22px;
  cursor: pointer;
  vertical-align: bottom;
  height: 240px;
}

.carousel-transaction {  
  display: inline-flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  
  width: 640px;
  height: 300px;

  background: #c2c0c000;
  border:1px solid rgb(252, 168, 168);
}

.slide {
  flex: 0 0 120px;
  height: 120px;
  margin: 10px;

  display: flex;
  justify-content: center;
  align-items: center;

  /*border: 2px dashed #000;
  border-radius: 50%;*/

  transition: transform 0.3s ease-in-out;
}

.slide:first-of-type {
  opacity: 0;
}

.slide:last-of-type {
  opacity: 0;
}
</style>
