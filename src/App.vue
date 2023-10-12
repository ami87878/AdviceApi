<template>
  <div class="base">
  <div id="app">
    <the-card class="the-card"></the-card>
  </div>
</div>
</template>

<script>

import TheCard from './components/TheCard.vue';
export default {
  name: 'App',
  components: {
    TheCard,
  }
}
</script>

<style lang="scss">
//layout
$sm:375px;
$lg:1440px;
//layout

//colors
//primary

$LightCyan: hsl(193, 38%, 86%);
$NeonGreen: hsl(150, 100%, 66%);

//Neutral

 $GrayishBlue: hsl(217,19%,38%);
 $DarkGrayishBlue: hsl(217,19%,24%);
 $DarkBlue: hsl(218, 23%, 16%);



//Neutral

//colors


//font size
$Fontsize: 28px;
//font size
@font-face {
  font-family: 'Manrope';
  src: url('https://fonts.google.com/specimen/Manrope');
}

$Weights: 800;


*{


  margin: 0;
  padding: 0;
  box-sizing: border-box
}


#app{
  
width: 100vw;

height: 70vh;


}

.the-card{

 
}
</style>
