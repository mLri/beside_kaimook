<template>
  <div class="ring">Loading</div>
</template>

<script>

export default {
  name: "spinner",
  data() {
    return {
    };
  },
  methods: {
    
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
body{
  margin: 0;
  padding: 0;
  background: #262626;
}
.ring
{
  position: absolute;
  /*Moves the word loading down and into the center of the page*/
  top: 50%;
  left: 50%;
  /*Moves the circle and loading word to the center of the page*/
  transform: translate(-50%,-50%);
  width: 150px;
  height: 150px;
  /*Makes the word loading have a transparent background*/ 
  background: transparent;
  /*Creates a square*/
  border: 3px solid #3c3c3c;
  /*turns the square to a circle*/
  border-radius: 50%;
  /* Aligns the word Loading to the right so it is in the center of the circle*/
  text-align: center;
  /*Moves the word Loading down and into the center of the circle*/
  line-height: 150px;
  /*Set font type*/
  font-family: sans-serif;
  /*Size font*/
  font-size: 20px;
  /*Sets font color*/
  color: blue;
  /*Spaces out letters*/
  letter-spacing: 4px;
  /*makes text uppercase*/
  text-transform: uppercase;
  /*To create glow effect*/
  text-shadow: 0 0 10px blue;
  /* Creates dark shadow around circle*/
  box-shadow: 0 0 20px rgb(0,0,0,.5);
}
/*Creates yellow spinner ring*/
.ring:before
{
  content: '';
  position: absolute; 
  /*originally set to 0px, but it was off, so changed to -3px to align with the loading circle*/
  top: -3px;
  left: -3px;
  width: 100%;
  height: 100%;
  /*Creates half a circle for the spinner portion*/
  border: 3px solid transparent;
  /*creates only top and right square border portion*/
  border-top: 3px solid blue;
  border-right: 3px solid blue;
  /*turns the box radius into a half circle :) */
  border-radius: 50%;
  /*creates animation*/
  animation: animateCircle 2s linear infinite;
}
/*Creates dial for the spinner to follow*/
span 
{
  /*display: block; starts a new line for the HTML span element*/ 
  display: block;
  position: absolute;
  /* The calc() function takes a single expression as its parameter, with the expression's result used as the value */
  top: calc(50% - 2px);
  left: 50%;
  width: 50%;
  height: 4px;
  background: transparent;
  transform-origin: left;
  animation: animate 2s linear infinite;  
}
/*creates the ball for the spinner to follow*/
span:before 
{
  content: '';
  position: absolute;
  width: 16px;
  height: 16px;
  border-radius: 50%;
  background: blue;
  /*moves the ball to the top of the line created in the previous span*/
  top: -6px;
  right: -8px;
  box-shadow: 0 0 20px blue;
}
/*Now the fun part, the ring will move with the ball that we set with the animate and animateCircle variables*/
@keyframes animateCircle 
{
  0%
  {
    transform: rotate(0deg);
  }
  100%
  {
    transform: rotate(360deg);
  }
}
@keyframes animate
{
  0%
  {
    transform: rotate(45deg);
  }
  100%
  {
    transform: rotate(405deg);
  }
}
/*followed tutorial on YouTube for guidance*/
</style>
