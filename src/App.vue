<template>
 <center> <h1>
  TIC TAC TOE</h1></center>
  <center>
  <br>
  <br>
  <button @click="alterplay">PLAY</button>
  <button @click="reset">STOP</button>
  </center>
  <center>
  
  <h2 id="xuf">1st player:potato</h2>
  <br>
  <h2 id="xuf2">
  2nd player:carrot
  </h2>
  </center>
  <center>
  <br>
  <br>
  <br>
  <br>
  <br>

  <span @click="ss(1)" id="1">
 {{ar2[0]}}
  </span>
  <span @click="ss(2)" id="2">
 {{ar2[1]}}
  </span>
   <span @click="ss(3)" id="3">
  {{ar2[2]}}
  </span>
  <p>
  </p>
  <br>
  <br>
   <br>
   <br>
   <br>
   <br>
   <span @click="ss(4)" id="4">
  {{ar2[3]}}
  </span>
  <span @click="ss(5)" id="5">
  {{ar2[4]}}
  </span>
   <span @click="ss(6)" id="6">
  {{ar2[5]}}
  </span>
  <p>
  </p>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
   <span @click="ss(7)" id="7">
  {{ar2[6]}}
  </span>
  <span @click="ss(8)" id="8">
  {{ar2[7]}}
  </span>
  <span @click="ss(9)" id="9">
  {{ar2[8]}}
  </span>
  <br>
 

  </center>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data (){
    return{
      isplaying:false,
      arra:[1,2,3,4,5,6,7,8,9],
      ar2:['NIll','Nill','Nill','Nill','Nill','Nill','Nill','Nill','Nill'],
      mine:true
    }
  },
  methods:{
    alterplay(){
      this.isplaying=!this.isplaying;
      alert("your game started");

    },
    turt(){
      
    },
  
    ss(id){
      
      if(this.isplaying==false){
        alert("pls clicl on play game before starting game"+id);
      }else{
     
       
        var x=id-1;
      
        
       
           if(this.arra.includes(id)){
             
                   if(this.mine==true){
               
               this.ar2[x]='p';
                this.mine=false;
                var el = document.getElementById("xuf2");
                  el.style.color = "red";
                var el1 = document.getElementById("xuf");
                  el1.style.color = "black";
               
              }else{
               
                  this.ar2[x]='c';
                this.mine=true;
                 var el = document.getElementById("xuf");
                  el.style.color = "red";
                   var el1 = document.getElementById("xuf2");
                  el1.style.color = "black";
               
              }
              const index = this.arra.indexOf(id);
                if (index > -1) {
                  this.arra.splice(index, 1);
                }
                
               
       var va=-1;
      if(this.ar2[0]=='p' && this.ar2[1]=='p' && this.ar2[2]=='p'){
            va=1;
      }else if(this.ar2[4]=='p' && this.ar2[3]=='p' && this.ar2[5]=='p'){
        va=1;}
      else if(this.ar2[6]=='p' && this.ar2[7]=='p' && this.ar2[8]=='p'){
        va=1;
      }else if(this.ar2[0]=='p' && this.ar2[3]=='p' && this.ar2[6]=='p'){
        va=1;
      }else if(this.ar2[1]=='p' && this.ar2[4]=='p' && this.ar2[7]=='p'){
        va=1;
      }else if(this.ar2[2]=='p' && this.ar2[5]=='p' && this.ar2[8]=='p'){
        va=1;
      }else if(this.ar2[0]=='p' && this.ar2[4]=='p' && this.ar2[8]=='p'){
        va=1;
      }else  if(this.ar2[0]=='c' && this.ar2[1]=='c' && this.ar2[2]=='c'){
            va=0;
      }else if(this.ar2[4]=='c' && this.ar2[3]=='c' && this.ar2[5]=='c'){
        va=0;}
      else if(this.ar2[6]=='c' && this.ar2[7]=='c' && this.ar2[8]=='c'){
        va=0;
      }else if(this.ar2[0]=='c' && this.ar2[3]=='c' && this.ar2[6]=='c'){
        va=0;
      }else if(this.ar2[1]=='c' && this.ar2[4]=='c' && this.ar2[7]=='c'){
        va=0;
      }else if(this.ar2[2]=='c' && this.ar2[5]=='c' && this.ar2[8]=='c'){
        va=0;
      }else if(this.ar2[0]=='p' && this.ar2[4]=='p' && this.ar2[8]=='p'){
        va=0;
      }
      
      if(va==1){
        alert("POTATO WON");
        this.isplaying=false;
       this.ar2=['NIll','Nill','Nill','Nill','Nill','Nill','Nill','Nill','Nill'];
       this.arra=[1,2,3,4,5,6,7,8,9];
       this.mine=true;
        var el = document.getElementById("xuf");
                  el.style.color = "red";
                   var el1 = document.getElementById("xuf2");
                  el1.style.color = "black";
      }else if(va==0){
         alert("CARROT WON");
          this.isplaying=false;
         this.ar2=['NIll','Nill','Nill','Nill','Nill','Nill','Nill','Nill','Nill'];
         this.arra=[1,2,3,4,5,6,7,8,9];
         this.mine=true;
          var el = document.getElementById("xuf");
                  el.style.color = "red";
                   var el1 = document.getElementById("xuf2");
                  el1.style.color = "black";
      }else{
        if(this.arra.length==0){
          alert("ITS A TIE");
           this.isplaying=false;
            this.ar2=['NIll','Nill','Nill','Nill','Nill','Nill','Nill','Nill','Nill'];
            this.arra=[1,2,3,4,5,6,7,8,9];
            this.mine=true;
             var el = document.getElementById("xuf");
                  el.style.color = "red";
                   var el1 = document.getElementById("xuf2");
                  el1.style.color = "black";
        }
      }
             
           }else{
             alert("This block is already selected select another block" );
           }
             
            
      }

    },
     reset(){
       alert("GAME STOPPED");
       this.isplaying=false;
       this.arra=[1,2,3,4,5,6,7,8,9];
            this.ar2=['NIll','Nill','Nill','Nill','Nill','Nill','Nill','Nill','Nill'];
        this.mine=true;
         var el = document.getElementById("xuf");
                  el.style.color = "red";
                   var el1 = document.getElementById("xuf2");
                  el1.style.color = "black";
    }
    }
   
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  background-color:#eee;
  border-radius:25px;
  margin:10px 10px;
  border:5px;
  padding:5px;
  width:200px;
}
button{
  width:100px;
  color:crimson;
  border-radius:3px;
  height:35px;
}
span{
 
margin:7px;
border-radius:4px;
border-color:#f0ffff;
padding:50px;
background-color:#96ded1;
width:50px;
}
#xuf{
  font:bold;
  color:red;
}
</style>
