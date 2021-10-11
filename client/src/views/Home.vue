<template>
  <BasicLayouts>
</BasicLayouts>

            <div class="banner">
              
            </div>

      
         <div class="services">
             <h1>Compra Productos Inteligentes</h1>
        </div>

        <section  class="services-section">

           
          
            <article >
                

                <router-link class="item" to="/redes-inalambricas" > 
                  <img  src="../assets/antenas.jpg" alt="Redes Inalambricas" >
                 </router-link>  
                    <h2 >Redes Inalambricas</h2>
                 
                    <p >
                       Transmision de datos y video a largas distancias implementando redes inalámbricas con tecnologías microondas
                    </p>
            </article>

            <article >
               <router-link class="item" to="/seguridad-electronica" > 
                <img  src="../assets/camaras.jpg" alt="Seguridad Electronica">
                </router-link> 
                <h2 >Seguridad Electronica</h2>
                <p>
                    Implemente las soluciones tecnologias mas avanzadas en seguridad electrónica para vigilar su negocio y hogar.
                </p>
            </article>

            <article class="domotica">

              <router-link class="item" to="/domotica" > 
                <img  src="../assets/domotica1.jpg" alt="Domotica" >
                </router-link> 

                <h2 >Domotica</h2>
                <p >
                    Diseñe una casa inteligente con la mas avanzada tecnología domotica en control e iluminación.
                </p>
            </article>

        </section>
       

    

    
    

  <footer class="footer">
        <article>
           <p>Copyright © 2021 SisteLing- soluciones inteligentes Todos los derechos reservados.</p>
        </article> 
    </footer>  
 
   
</template>



<script>
import { ref, onMounted } from 'vue';
import{useRouter }from 'vue-router';
import BasicLayouts from '../layouts/BasicLayouts.vue';
import{}from '../api/category';


export default {
  name: 'Inicio',
  components: {
    BasicLayouts,
    
  }
  
};

</script>

<style scoped>



.banner {
  width: 100%;
  height: 500px;
  max-width: 100%;
  object-fit: cover;
  display: block;
  margin: auto;
  background-size: cover;
  background-size: 100% 100%;
  animation: banner 20s infinite;
  animation-direction:alternate;
  background-image: url("../assets/banner1.jpg");
}

/* @keyframes banner{
  0%, 30% {
    background-image: url("../assets/banner1.jpg");
  }

  31%,34%{
    opacity:0.1;
  }
  35%, 65% {
    background-image: url("../assets/banner2.jpg");
    opacity: 1;
  }
  66%,69%{
    opacity: 0.1;
  }
   70%, 100% {
     opacity: 1;
    background-image: url("../assets/banner3.jpg");
  }
} */

.services{
  /*background-color: #3689d6;*/
  background-image: url('../assets/header1.jpg');
  height: 100px;
  color: white;
  /*Para centrar un contenido*/
  display: flex;
  justify-content: center;
  align-items: center;
  
}

.header-container {
  background-color: #f7f7f7;
}
.services-section {
  display: flex;
  align-items: center; 
  
}

.services-section article {
  padding: 20px;
  text-align: center;
}

.services-section img {
  border-radius: 60%;
  margin-right: auto;
  margin-left: auto;
  width: 60%;
  height: 60%;
  margin-bottom: 30px;
}

.domotica{
   margin-bottom: 10px;
}
.services-section p {
  font-size: 20px;
  text-align:center;
  
}

.footer {
  background-color: #25294f;
  height: 150px;
  display: flex;
  color: white;
  justify-content: space-evenly;
}

footer p {
  font-size: 20px;
}

</style>