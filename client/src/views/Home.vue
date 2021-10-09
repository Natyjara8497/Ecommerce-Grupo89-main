<template>
  <BasicLayouts>
</BasicLayouts>
<body>
  
  
            <div class="banner">
              
                <img src="../assets/domotica1.jpg" alt="Sisteling" width="1900" height="500"  >
               
            </div>

       

       
         <div class="services">
             <h1>Compra Productos Inteligentes</h1>
        </div>

        <section  class="services-section">

           
          
            <article >
                

                <router-link class="item" to="/redes-inalambricas" > 
                  <img  src="../assets/antenas8.jpg" alt="Redes Inalambricas" >
                 </router-link>  
                    <h2 >Redes Inalambricas</h2>
                 
                    <p >
                        Conectamos datos y video a largas distancias a través de redes inalámbricas usando tecnologías microondas
                    </p>
            </article>

            <article >
               <router-link class="item" to="/seguridad-electronica" > 
                <img  src="../assets/camaras1.jpg" alt="Seguridad Electronica">
                </router-link> 
                <h2 >Seguridad Electronica</h2>
                <p>
                    Ofrecemos un sistema completo de seguridad electrónica para vigilar su negocio y hogar.
                </p>
            </article>

            <article class="domotica">

              <router-link class="item" to="/domotica" > 
                <img  src="../assets/domotica4.jpg" alt="Domotica" width="60" height="60">
                </router-link> 

                <h2 >Domotica</h2>
                <p >
                    Diseñamos su casa inteligente con la mas avanzada tecnología de control e iluminación.
                </p>
            </article>

        </section>
       

    

    
    

  <footer class="footer">
        <article>
           <p>Copyright © 2021 SisteLing- soluciones inteligentes Todos los derechos reservados.</p>
        </article> 
    </footer>  
  </body>
   
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

<style >


.banner {
  width: 100%;
  height: 500px;
  max-width: 100%;
  object-fit: cover;
  display: block;
  margin-left: auto;
  margin-right: auto;
  background-size: cover;
}

.services{
  /*background-color: #3689d6;*/
  background-image: url('../assets/header10.jpg');
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