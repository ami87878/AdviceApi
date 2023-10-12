<template>
    
    <div class="card__wrapper">
        <main class="main1">
            <h3>ADVICE # {{number}}</h3>
            <AdviceContent>

                {{ advice }}

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
            number:'',
            advice:''
        
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
            this.number=json.slip.id
             
             console.log('this is advice',json.slip.advice);
        

        
            
            

        },




        
        
    },

    watch:{

        



    }
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

.dice:hover{

 -webkit-box-shadow: 1px 0px 23px 14px #5CFFA5; 
box-shadow: 1px 0px 23px 14px #5CFFA5;
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

    position: relative;
}
.main1{

    display: flex;
    flex-direction: column;
   background-color:$DarkGrayishBlue; 
   width: 100%;
   min-height: 300px;
   border-radius: 15px;
   
   
}

@media screen and (max-width:375px) {


    .card__wrapper{
        width: 60%;
        margin-left: 40%;
    }
    
}
@media screen and (max-width:375px ) {

    .card__wrapper{
        width: 80%;
        margin-left: 10%;
    }

    .line__container{

        width: 80%;
        margin-left: 10%;

    }

    
}
@media screen and (min-width:375px ) {

    .card__wrapper{
        width: 80%;
        margin-left: 10%;
    }

    .line__container{

        width: 80%;
        margin-left: 10%;

    }

    .dice{
    
        margin-top: 2%;
    }

    
}

@media screen and (min-width:462px ){

    .dice{
        margin-top: 5%;
    }
}
@media screen and (max-width:1440px ){


    
    .card__wrapper{
       
        width: 50%;
        margin-left: 25%;
        margin-top: 8%;
    
    }

    .line__container{

        width: 80%;
        margin-left: 10%;

    }

    .dice{

    width: 11%;
    margin-top: 0.5%;
    }
    
}

</style>