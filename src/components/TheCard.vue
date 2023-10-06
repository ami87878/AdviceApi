<template>
    
    <div class="card__wrapper">
        <main class="main1">
            <h3>ADVICE #117</h3>
            <AdviceContent>

                {{ message }}
               </AdviceContent>

               <div class="line__container">
                
                <img src="../assets/pattern-divider-desktop.svg">
                
            </div>

         
         <section id="dice-wrapper">
            <div class="dice" @click="fechFunc">

            <img src="../assets/icon-dice.svg" >

           </div>
        </section>

               <green-cricle>

               </green-cricle>
               


        </main>
    </div>
    
</template>

<script>

import AdviceContent from './AdviceContent.vue';
import Greencricle from './GreenCricle.vue'
export default {


    comments:{
       
        AdviceContent,
        Greencricle,

    },
    name: 'TheCard',

    data() {
        return {
            message:'',
            advice:'',
        
        };
    },

    mounted() {
        
    },

    computed:{

    


    },

    methods: {

        async fechFunc(){

           
            const response=await fetch('https://api.adviceslip.com/advice');
    
            const json=await response.json();

             this.advice=json.slip.advice;
            
            console.log('this.advice',this.advice);
            console.log('this is advice',json.slip.advice);

            this.message=this.advice;
            

        },


        
        
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
$NeonGreen: #52ffa8;

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
  src: url('../assets/static/Manrope-Regular.ttf');
}

$Weights: 800;


*{


  margin: 0;
  padding: 0;
  box-sizing: border-box
}


#dice-wrapper{

   border: 2px solid red;
   display: flex;
   justify-content: center;
   align-items: center;
   
   
   
}

.dice{

    background-color: $NeonGreen;
    padding: 5%;
    width:16% ;
    border-radius: 50%;
    margin-top: 6%;
    display: flex;
    justify-content:center;
    align-items: center;
    position: absolute;
    top: 82%;
    cursor: pointer;  
    
}



.dice:hover::after{

   
    background: rgb(82,255,168);
background: radial-gradient(circle, rgba(82,255,168,1) 0%, rgba(82,255,178,0.8463585263206845) 48%, rgba(99,255,177,1) 81%); 

    
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
border: 2px solid blue;

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
    
    width: 80%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-left: 12%;
    text-align: center;
    border: 2px solid orange;

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
    border: 2px solid rgb(255, 0, 179);
    position: relative;
}
.main1{

    display: flex;
    flex-direction: column;
   background-color:$DarkGrayishBlue; 
   width: 100%;
   min-height: 300px;
   border-radius: 15px;
   border: 2px solid rgb(0, 204, 255);
   
}

</style>