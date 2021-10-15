<template>
  <BasicLayouts>
</BasicLayouts>

            <div class="banner">
              
            </div>

      
         <div class="services">
             <h1>Servicios de transporte especial</h1>
        </div>

        <section  class="services-section">

           
          
            

            <article >
               <router-link class="item" to="/Turismo" > 
                <img  src="../assets/Viajes.jpg" alt="Turismo">
                </router-link> 
                <h2 >Turismo</h2>
                <p>
                    Te llevamos por todas las carreteras para que conozcas colombia
                </p>
            </article>

            <article >
                

                <router-link class="item" to="/Transporte empresarial" > 
                  <img  src="../assets/empresarial.jpg" alt="Transporte empresarial" >
                 </router-link>  
                    <h2 >Transporte empresarial</h2>
                 
                    <p >
                       Como tu personal es lo mas importante lo transportamos hacia su sitio de trabajo de maneja segura
                    </p>
            </article>

            <article class="escolar">

              <router-link class="item" to="/Escolar" > 
                <img  src="../assets/Escolar.jpg" alt="Escolar" >
                </router-link> 

                <h2 >Escolar</h2>
                <p >
                    Transportamos tus hijos con seguridad y confianza.
                </p>
            </article>

        </section>
       

    

    
    

  <footer class="footer">
        <article>
           <p>Copyright © 2021 MoviFast- Transportando de manera segura.</p>
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
  background-size: 95% 95%;
  animation: banner 20s infinite;
  animation-direction:alternate;
  background-image: url("../assets/logo.jpg");
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
  background-image: url('../assets/fondo negro.jpg');
  height: 100px;
  color: rgb(250, 248, 246);
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
  width: 75%;
  height: 50%;
  margin-bottom: 30px;
}

.escolar{
   margin-bottom: 10px;
}

.services-section p {
  font-size: 20px;
  text-align:center;
  
}

.footer {
  background-color: #092417;
  height: 150px;
  display: flex;
  color: white;
  justify-content: space-evenly;
}

footer p {
  font-size: 20px;
}

</style>