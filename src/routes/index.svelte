<svelte:head>
	<title>La Quinta Maravilla</title>
</svelte:head>
<script>
import { fly } from 'svelte/transition';
let mOption = 0;
let pOption = 0;
var paquete = 'aventura';
var paqText = 'Al acampar, suministramos el equipo completo de camping. todos los alojamientos, incluyendo las tiendas de campaña, se establecen sobre la base de la ocupación doble. De vez en cuando podríamos permanecer en cabañas de madera o una yurta local como estilo dormitorio. Esto es parte de la experiencia de unas vacaciones de aventura y se requiere un enfoque flexible. ';
var text = new String();
var texto = new Array();

texto[0] = "Hospedaje tipo Camping, nos llamamos La Quinta Maravilla y te brindaremos el Confort que te mereces.";

texto[1] = "Conoce el hermoso cañon el sumidero en Tuxtla Gutierrez Chiapas uno de los estados mas hermosos de todo Mexico";
text = texto[0];
var x = 0;
var details = new Array();
function chgtext (){
  paqText = details;
}
function chgCnt1(){
  if(x>0)
  x--;
  console.log(x);
  text = texto[x];
  document.getElementById('welcome_img').style.backgroundImage = "url('https://i.imgur.com/OhnObZc.jpg')";
}
function chgCnt2(){
  if(x<texto.length - 1)
  x++;
  console.log(x);
  text = texto[x];
  document.getElementById('welcome_img').style.backgroundImage = "url('https://i.imgur.com/NUB8i04.jpg')";
}
var scrWidth = window.matchMedia("(max-width: 1023px)")

function paventura(){
  paquete = 'aventura';
  pOption = 0;
  paqText = 'Al acampar, suministramos el equipo completo de camping. todos los alojamientos, incluyendo las tiendas de campaña, se establecen sobre la base de la ocupación doble. De vez en cuando podríamos permanecer en cabañas de madera o una yurta local como estilo dormitorio. Esto es parte de la experiencia de unas vacaciones de aventura y se requiere un enfoque flexible.';
  
    if(scrWidth.matches){
    document.getElementById('activities').style.backgroundImage = "url('https://i.imgur.com/H2yACAJ.jpg')";
    
  }
  else{
    document.getElementById('paq_c').style.backgroundImage = "url('https://i.imgur.com/H2yACAJ.jpg')";
  }
  
}
function promance(){
paquete = 'romance';
pOption = 1;
paqText = 'Una noche especial para compartir con esa persona especial. Nuestro paquete para dos personas con: hospedaje por una noche camping.';

  if(scrWidth.matches){
    document.getElementById('activities').style.backgroundImage = "url('https://i.imgur.com/1Rvx3eU.jpg')";
    
  }
  else{
    document.getElementById('paq_c').style.backgroundImage = "url('https://i.imgur.com/1Rvx3eU.jpg')";
  }
}
function prelajacion(){
  paquete = 'relajacion';
  pOption = 2;
  paqText = 'Vive todos los atractivos que el cañón del sumidero te ofrece, adentrándote en sus bellas aguas, disfrutando de un momento de relajación. Y para tener un descanso completo disfruta de un masaje escuchando el cantar de la fauna que este atractivo paquete te ofrece ';
  
  if(scrWidth.matches){
    document.getElementById('activities').style.backgroundImage = "url('https://i.imgur.com/X0y1iIg.jpg')";
    
  }
  else{
    document.getElementById('paq_c').style.backgroundImage = "url('https://i.imgur.com/X0y1iIg.jpg')";
  }
  
  
}

function mb(){
  mOption = 0;
  deployMenu();
}
function ma(){
  mOption = 1;
  deployMenu();
}
function mc(){
  mOption = 2;
  deployMenu();
}

var menuD = 0;

function deployMenu(){
  if(scrWidth.matches){
      if(menuD === 0){
    document.getElementById('mn').style.left = "0px";
    menuD = 1;
  }
  else{
    document.getElementById('mn').style.left = "-50vw";
    menuD = 0;
  }
  }

  

}

</script>

<style>
  /* Colors
  Azul cielo = #6fc6c0
  gold = #c6996f
  
  */
  @import url('https://fonts.googleapis.com/css2?family=Kaushan+Script&display=swap');
 :global(*) {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
:global(body, div) {
  font-family: 'Kaushan Script', cursive;
  margin: 0;
  padding: 0;
}
  .bg {
    position: fixed;
    z-index: 0;
  }

  #mn {
    position: fixed;
    top: 0;
    left: 0;
    display: flex;
    align-items: center;
    width:100vw;
    justify-content: space-between;
    background-color: #131212;
    
    box-shadow: 0px 0px 50px 0px rgba(0,0,0,1);
  }

  .image_logo{
    width: 8vh;
    border-radius: 50%;
  }
  .menu_items {
    
    display: flex;
    list-style: none;  
    align-items: center;
    justify-content: space-evenly;
    width: 100vw;  
    height: 9vh;
  }

  .ml{
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 22.5px;
    color: beige;
    height: 100%;
    width: 33%;
    transition: 1s;
  }

  li:hover{
    background-color: #b1f3ef46
  }

 .app_content{
   background-color: rgba(0, 0, 0, .3);
   position: absolute;
   z-index: 0;
   top: 9vh;
   height: 91vh;
   width: 100vw;
   display: grid;
   grid-template-columns: .15fr 1fr .15fr;
   grid-template-rows: .15fr 1fr .15fr;
   grid-template-areas: ". paq ."
                        "le ct ri"
                        ". . .";
   
   
   
  
 }

 .grid_item {
   display: flex;
   color:#6fc6c0;
   font-size: 36px;
   justify-content: center;
   align-items: center;
 }

 #welcome{
   display: grid;
   grid-template-columns: .1fr .75fr 1fr .1fr;
   grid-template-rows: 1fr 1fr;
   grid-template-areas: ". cont img img"
                        ". cont img img";

   transition: 2s all;
   border: 2px solid #131212;
   background-color: #c6996f7c;
   height: 100%;
   width: 100%;
   box-shadow: 20px 20px 20px 20px rgba(0,0,0,1);
 }

  #welcome_img{
    grid-area: img;
    background-color: white;
    background-image: url('https://i.imgur.com/OhnObZc.jpg');
    background-repeat: no-repeat;
    background-size: cover;
    box-shadow: -20px -20px -20px -20px rgba(0,0,0,1);
    transition: 2s;
  }

  #ct{
    grid-area: ct;
  }

  #le{
    grid-area: le;
  }
  #ri{
    grid-area: ri;
  }

  .arrows{
    display: flex;
    align-items: center;
    justify-content: center;
    color: #131212;
    background-color: rgba(255,255,255,0.35);
    height:64px;
    width:64px;
    border-radius: 50%;
    align-self: center;
    justify-self: center;
  }

  #welcome_cont{
    grid-area: cont;
    display: flex;
    align-items: center;
    justify-content: center;
  
  }

  .welcome_title{
    padding: 5px;
    padding-right: 55px;
    color: whitesmoke;
  }

 #activities {
      display: grid;
   grid-template-columns: minmax(520px, auto) 1.75fr;
   grid-template-rows: .1fr 1fr;
   grid-template-areas: "paq_title img"
                        ". img"  ;

  transition: 2s all;
   border: 2px solid #131212;
   background-color: #c6996f79;
   height: 100%;
   width: 100%;
   box-shadow: 20px 20px 20px 20px rgba(0,0,0,1);
 }

 #contact_us{
   display: grid;
   grid-template-columns: 1fr 1fr;
   grid-template-rows: 1fr 1fr 1fr;
   transition: 2s all;
   border:2px solid #131212;
   background-color: #c6996f7c;
   height: 100%;
   width: 100%;
   box-shadow: 20px 20px 20px 20px rgba(0,0,0,1);
 }
  .paquetes{
    display: flex;
    align-items: center;
    grid-area: paq;
  }

  .paquetes_items{
    width: 100%;
    height: 100%;
    display: flex;
    list-style: none;  
    align-items: center;
    justify-content: space-evenly;

  }

  .pl{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 50%;
    background-color: rgba(0, 0,0 , .65);
    color: aliceblue;
    border: solid 1px #c6996f;
    transition: 1.5s;
    font-size: 150%;
  }

  .paq_title{
    color:white;
    text-align: center;
  }
  .paq_cont{
    display: flex;
    grid-area: img;
    color: white;
    justify-content: center;
    align-items: center;
    
    
  }

  #paq_c{
    background-image: url('https://i.imgur.com/H2yACAJ.jpg');
    background-size: cover;
    transition: 1s;
  }
  .paq_list{
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
  }
  .contText{
    max-width: 95%;
    background-color: rgba(0, 0, 0, 0.596);
    max-height: 95%;
    font-size: 24px;
    border-radius: 20px;
    border:solid white 1px;
    padding: 12px;
  }



  .liav{
    
    color: #131212;
    font-size: 24px;
  }

  .buyButton{
    
    border:none;
   
    background: #c6996f;
    font-family: Arial, Helvetica, sans-serif;
    max-height: 72px;
         min-height: 2em;
    width: 40%;
    color: aliceblue;
  }

  .buyButton:hover{
    background-color: rgba(240, 248, 255, 0.37);
  }
  .paq_img{
    
    border-radius: 50%;
    width: 40%;
  }

  .img_f{
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .App{
    position: fixed;
  }
  .sub_items{
    display: grid;
    grid-template-columns: 115px 1fr;
    justify-content: space-around;
    align-items: center;
  }
    .sub_item-info {
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      justify-content: space-evenly;
    margin-left: 10px;
    padding-left: 10px; 
    background-color: rgba(0, 0,0 , .65);
    border: solid white 1px;
    border-radius: 10px;
    min-height: 140px;
    
  }
  .sub_item-info p,a{
    color: white;
    font-weight: bold;
    
    font-size: 24px;
    text-decoration: none;
    
  }
  .cont_img {
      max-width: 115px;
      overflow: hidden;
  }

  .cont_img img{
    border-radius: 50%;
    max-height: 140px ;
    max-width: 150px;
    
  }


  /*Responsive 1366px*/
  @media (max-width:1365px){
        .app_content{
              grid-template-areas:
        "paq paq paq"
        "ct ct ct"
        "le . ri";
        }
        .pl{
          height: 100%;
          border:none;
        }
        figure{
          all:unset;
        }
        .paq_img{
              
              width: 100px;
             
        }

        .paq_title{
          font-size: 70%;
        }
       
  }
  @media (max-width:1023px){
    #mn{
      background-color: #1312127a;
      flex-direction: column;
    align-items: self-start;
    width: 50vw;
    left:-50vw;
    height: 100vh;
    z-index: 1;
        justify-content: flex-start;
        transition: 2s;
    }
    .menu_items{
      
      
      width: 100%;
      height: 100%;
      flex-direction: column;
    }
    .ml{
      width: 100%;
    }
    .logo{
      position: fixed;
      top:0;
      left:0;
      opacity: .3;
    }
   
            .app_content{
              grid-template-areas:
        "paq paq paq"
        "ct ct ct"
        "ct ct ct";
      top: 0;
      height: 100vh;
        }
        #le{
          display: none;
          grid-area: unset;
        }
        #ri{
          display: none;
          grid-area: unset;
        }

        #welcome{
          grid-template-areas:
        "cont cont cont cont"
        "cont cont cont cont";
        background-image: url('https://i.imgur.com/NUB8i04.jpg');
        background-size: cover;
        }
        #welcome_img{
          display: none;
        }
        #welcome_cont{
          justify-content: center;
          align-items: flex-start;
        }
        .welcome_title{
          padding: 0;
          padding-left: 5%;
          margin-top: 10%;
          
        }

     #activities {
  
            grid-template-rows: auto 1fr;
    grid-template-columns: 1fr;
        grid-template-areas: "paq_title "
                               "img" ;   
        background-image: url("https://i.imgur.com/H2yACAJ.jpg");
        background-size: cover;
        height: 100%;
        width: 100%;
        box-shadow: 20px 20px 20px 20px rgba(0,0,0,1);
 }
  .paq_title{
    grid-area: paq_title;
    text-align: left;
    padding: 1%;
    padding-left: 5%;
    background-color: rgba(0, 0, 0, 0.596);
  }
  #paq_c{
    background-image: unset;
  }
  .contText{
    font-size: .5em;
  }
  .liav{
    font-size: .5em;
    color: aliceblue;
  }
  .paq_list{
    background-color: rgba(0, 0, 0, 0.596);
  }
  .sub_item-info{
    min-height: 80px;
  }
  .sub_item-info p,a{
    font-size: 14px;
    
  }
  #contact_us{
    grid-template-columns: 1fr;
    grid-template-rows: repeat(6,6fr);
    }
    .cont_img img{
      max-height: 80px;
    }
  }

</style>
  <figure class="bg">
    <img src="https://i.imgur.com/fMS5g12.jpg" alt="">
  </figure>
<div class="App">

  <section class="menu" id="mn">
    <figure class="logo" id='menu_bt'>
      <img src="https://i.imgur.com/9FIULiK.jpg?1" alt="" class="image_logo" on:click={deployMenu}>
    </figure>
    <ul class="menu_items">
      <li class="ml" on:click = {mb}>Bienvenido</li>
      <li class="ml" on:click = {ma}>Paquetes</li>
      <li class="ml" on:click = {mc}>Contactanos</li>
    </ul>
  </section>
<div class="app_content">
  {#if mOption == 0}
  <div class="arrows" id="le" on:click = {chgCnt1}>◄</div>
  <div class="arrows" id="ri" on:click = {chgCnt2}>►</div>  
  {/if}

    {#if mOption == 1}
     <div class="paquetes" id="paq">
        <ul class="paquetes_items">
          <li class="pl" on:click = {paventura} > Aventura</li>
          <li class="pl" on:click = {promance}>   Romance</li>
          <li class="pl" on:click = {prelajacion}>Relajacion</li>
        </ul>
     </div>
     {/if}

  <div class="grid_item" id="ct">
     {#if mOption == 0}
        <div id="welcome" in:fly="{{ y: 100, duration: 1000 }}" out:fly="{{ y: 100, duration: 1 }}" >
          <div id="welcome_img"></div>
          <div id="welcome_cont"> 
            <div class="welcome_title"> 
              <p>
                {text}
              </p>
            </div>
        </div>
      </div>
      {/if}

     {#if mOption == 1}
      <div id="activities" in:fly="{{ y: 100, duration: 1000 }}" out:fly="{{ y: 100, duration: 1 }}">
        <div class="paq_title"><p> El paquete {paquete} incluye:</p></div>
        <div class="paq_cont" id="paq_c"><div class="contText">{paqText}</div></div>
        
        <div class="paq_list">
         {#if pOption == 0}
         <ul class="ulav">
          <li class="liav">1 noche y un día</li>
          <li class="liav">Incluye desayuno y una comida</li>
          <li class="liav">Recorrido por los miradores del cañón </li>
          <li class="liav">Noche de hospedaje en una cabaña</li>
          <li class="liav">Paseo en lancha</li>
         </ul>
         <figure class="img_f"><img class='paq_img' src="https://i.imgur.com/VmZEcqP.jpg" alt=""></figure>
         {/if}
         {#if pOption == 1}
         <ul class="ulav">
         <li class="liav"> Tienda de campaña (impermeable) <br> y Sleeping bag</li>
         <li class="liav">Linternas</li>
         <li class="liav">Muchas cobijas y Almohadas</li>
         <li class="liav">Navaja suiza</li>
         <li class="liav">Comida y Agua <br>(asado, chocolate caliente y mas)</li>
         <li class="liav">leña para fogata</li>
         <li class="liav">botella de vino.</li>
         
         </ul>
         <figure class="img_f"><img class='paq_img' src="https://i.imgur.com/xWD61jV.jpg" alt=""></figure>
         {/if}
         {#if pOption == 2}
         <ul class="ulav">
         <li class="liav">2 días y 1 noche</li>
         <li class="liav">1 noche de hospedaje </li>
         <li class="liav">3 comidas en el restaurante </li>
         <li class="liav">Circuito de tirolesas </li>
         <li class="liav">Temazcal </li>
         <li class="liav">Recorrido por el cañón del sumidero </li>
         <li class="liav">Masaje relajante</li>
         
         </ul>
         <figure class="img_f"><img class='paq_img' src="https://i.imgur.com/ZZ1VPKV.jpg" alt=""></figure>
         {/if}     

          <button class="buyButton">Buy Now!!</button>    
       </div>
        

      </div>
      {/if}
      

      {#if mOption == 2}
        <div id="contact_us" in:fly="{{ y: 100, duration: 1000 }}" out:fly="{{ y: 100, duration: 1 }}">
          <div class="sub_items">
            <figure class="cont_img"><img src="https://i.imgur.com/zUcE3qT.png" alt="" /></figure>
            <div class="sub_item-info">
              <p>Yessica Elizabeth Pérez Frías</p>
              <a href="yessicafrias9@gmail.com">yessicafrias9@gmail.com</a>
              <p>Directora del Proyecto</p>
            </div>
          </div>
          <div class="sub_items">
            <figure class="cont_img"><img src="https://i.imgur.com/8PnNIVO.png" alt="" /></figure>
            <div class="sub_item-info">
              <p>Camila Leticia Trejo de los Santos</p>
              <a href="camilinda36@gmail.com">camilinda36@gmail.com</a>
              <p>Recepcionista</p>
            </div>
          </div>
          <div class="sub_items">
            <figure class="cont_img"><img src="https://i.imgur.com/mVTztZE.png" alt="" /></figure>
            <div class="sub_item-info">
              <p>Daniel Elías García Pineda</p>
              <a href="danielpinedda98@gmail.com">danielpinedda98@gmail.com</a> 
              <p>Jefe de campamento</p>
            </div>
            
          </div>
          <div class="sub_items">
            <figure class="cont_img"><img src="https://i.imgur.com/JjXMdA7.png" alt="" /></figure>
            <div class="sub_item-info">
              <p>Alina Aguilar Figueroa</p>
              <a href="Figueroaalina689@gmail.com">Figueroaalina689@gmail.com</a> 
              <p>Auxiliar de Enfermería</p>           
            </div>

          </div>
          <div class="sub_items">
            <figure class="cont_img"><img src="https://i.imgur.com/BBl7Zje.png" alt="" /></figure>
            <div class="sub_item-info">
              <p>Alexis Hernández de la Rosa</p>
              <a href="Alexis0798@outlook.es">Alexis0798@outlook.es</a> 
              <p>Técnico en mantenimiento y vigilancia</p>           
            </div>

          </div>
          <div class="sub_items">
            <figure class="cont_img"><img src="https://i.imgur.com/ibhAkmL.png" alt="" /></figure>
            <div class="sub_item-info">
              <p>Fátima Daniela Pérez Sánchez</p>
              <a href="fperezsanchez14@gmail.com">fperezsanchez14@gmail.com</a> 
              <p>Jefe de contabilidad</p>
            </div>

          </div>
        </div>
      {/if}
  </div>
      

      

  </div>
 
</div>






