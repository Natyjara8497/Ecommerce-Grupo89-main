<template>
  
  <div class="ui secondary menu"> 
  
        

            <div class="contenedor">

                <div class="menu-container">

                    <div class="logo-container">
                        <img class="logo" src="../assets/logo1.jpg">
                        <h2>MoviFast</h2>
                    </div>
                        
                    <div id="menu" >
                        
                            <ul>
                                
                                <li> <router-link class="item" to="/">
                                               Nosotros
                                   </router-link></li>
                                   
                                <li> 
                                    <router-link class="item" to="/productos">
                                               Servicios
                                   </router-link>
                                    <ul> 
                                   <li v-for="category in categories" :key="category.id">
                                     <router-link class="item" :to="category.slug">
                                        {{ category.title }}
                                        
                                        </router-link>
                                    </li>
                                    </ul>
                                </li> 

                      
       
                 
                                <li> <router-link class="item" to="/login" v-if="!token">
                                   Iniciar Sesión</router-link> </li>

        <template v-if="token">
         <li> 
           <router-link class="item" to="/Cart">Pedidos</router-link>
        </li>

        <li> 
          <span class="ui item cart" @click="openCart" >
            <i class="shopping cart icon" ></i>
          </span>
        </li>

         <li> <span class="ui item logout" @click="logout">
            <i class="sign-out icon"></i>
          </span>

        </li>
        </template>
      
              </ul>                   
                           
                       
                            
                   </div>
 
            </div>
       </div>
      

 </div>
 
  



</template>

<script>
import { ref, onMounted } from 'vue';
import { useStore } from 'vuex';
import { getTokenApi, deleteTokenApi } from '../api/token';
import { getCategoriesApi } from '../api/category';

export default {
  name: 'Menu',

  setup() {
    let categories = ref(null);
    const token = getTokenApi();
    const store = useStore();

    onMounted(async () => {
      const response = await getCategoriesApi();
      categories.value = response;
    });

    const logout = () => {
      deleteTokenApi();
      location.replace('/');
    };

    const openCart = () => {
      store.commit('setShowCart', true);
    };

    return {
      token,
      logout,
      categories,
      openCart,
    };
  },
};
</script>

<style lang="scss" scoped>
.ui.menu.secondary {
  
  background-image: url('../assets/fondo2.jpg');
  .item {
    color: #ffffff;
    &:hover {
      color: #1a6899;
    
    }
  }
}
  
  
p {
  font-size: 20px;
  text-align: center;
}


h1 {
  font-size: 50px;
  margin: 0;
  color: #222222;
}

h2 {
  font-size: 50px;
  margin-bottom: 40px;
  color: #fffffff3;
  justify-content: center;
  align-items: center;
}


.header-section {
  margin-bottom: 50px;
}

.contenedor {
  width: 100%;
  margin: auto;
  
}

.logo-container {
  width: 10%;
  text-align: right;
  margin-bottom:2% ;
  

}
.logo-container h2{
 margin-top: 1%;
 text-align: center
 

}
.logo {
  height: 100px;
  
  
}

.menu-container {

  display: flex;
  justify-content: space-between;
  align-items: center;
  width:100%;
 
}

/* menu */

#menu{
 width: 30%;
}
#menu ul {
  list-style: none;
  margin: 0;
  padding: 0;
 
}



/* enlaces del menu */

#menu ul a{
  display: block;
  color: rgb(240, 243, 232);
  text-decoration: none;
  font-weight: 400;
  font-size: 15px;
  padding: 10px;
  font-family: "HelveticaNeue", "Helvetica Neue", Helvetica, Arial, sans-serif;
  text-transform: uppercase;
  letter-spacing: 1px;
}

/* items del menu */

#menu ul li {
  background-color: #32523f;
  position: relative;
  float: left;
  margin: 0;
  padding: 0;
}

/* efecto al pasar el ratón por los items del menu */

#menu ul li:hover {
  background: #7fe223;
}

/* menu desplegable */

#menu ul ul {
  display: none;
  position: absolute;
  top: 100%;
  left: 0;
  background: #eee;
  padding: 0;
}

/* items del menu desplegable */

#menu ul ul li {
  float: none;
  width: 150px;
}

/* enlaces de los items del menu desplegable */

#menu ul ul a {
  line-height: 120%;
  padding: 10px 15px;
}

/* items del menu desplegable al pasar el ratón */

#menu ul li:hover > ul {
  display: block;
}

</style>
