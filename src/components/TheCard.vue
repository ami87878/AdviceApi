<template>
    
    <div class="card__wrapper">
        <main class="main1">
            <h3>ADVICE #117</h3>
            <AdviceContent>'It is easy to sit
             up and take
              notice 
              ,what's difficult
               getting up 
               and taking 
               action. '</AdviceContent>

               <div class="line__container">

                
                <img src="../assets/pattern-divider-desktop.svg" alt="" srcset="">
                

               </div>


        </main>
    </div>
    
</template>

<script>

import AdviceContent from './AdviceContent.vue'
export default {


    comments:{
       
        AdviceContent,

    },
    name: 'TheCard',

    data() {
        return {
            
        };
    },

    mounted() {
        
    },

    methods: {
        
    },
};
</script>

<style lang="scss" scoped>

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

.vertical-line{

font-weight: bold;

}


h3{


    color: $NeonGreen;
    font-size: 14px;
   text-align: center;
   margin-top: 6%;
}




.line__container{
margin-top: 10%;

width: 70%;
margin-left: 15%;
display: flex;
height: 20%;
justify-content: center;
align-items: center;

}

.line__container>img{


width: 100%;

}

AdviceContent{
    margin-top: 8%;
    color:$LightCyan ;
    font-size: 22px;
    font-family:'Manrope' ;
    font-weight: $Weights;
    
    width: 70%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-left: 15%;
    text-align: center;
    letter-spacing: 10%;

}

.card__wrapper{

   
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-top: 13%;
    margin-left: 35%;
    min-height: 30%;
    width: 30%;
}
.main1{

    display: flex;
    flex-direction: column;
   background-color:$DarkGrayishBlue; 
   width: 100%;
   min-height: 300px;
   border-radius: 15px;
   
}

</style>