<template>
  <BasicLayouts>
    <div class="title">
      <h1>Resumen de la Compra</h1>
    </div>
    <table class="ui celled table" v-if="products">
      <thead>
        <tr>
          <th>Producto</th>
          <th>Cantidad</th>
          <th>Precio</th>
          <th></th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="product in products" :key="product.id">
          <td>{{ product.name }}</td>
          <td>{{ product.quantity }}</td>
          <td>$ {{ product.price }}</td>
          <td style="text-align: center">
            <i class="close icon" @click="deleteAllProductCart(product.id)"></i>
          </td>
        </tr>
        <tr>
          <td></td>
          <td>Total:</td>
          <td colspan="2">$ {{ getTotal() }}</td>
        </tr>
      </tbody>
    </table>

    <button class="ui button primary fluid">
      Generar pedido
    </button>

    <h3 v-if="!products">No tienes productos en el carrito</h3>
  </BasicLayouts>
</template>

<script>
import { ref,watchEffect } from 'vue';
import BasicLayouts from '../layouts/BasicLayouts.vue';
import { getProductsCartApi, deleteAllProductCartApi } from '../api/cart';

export default {
  name: 'Cart',
  components: {
    BasicLayouts,
  },
  setup() {
    let products = ref(null);
    let realoadCart = ref(false);

    watchEffect(async () => {
      realoadCart.value;
      const response = await getProductsCartApi();
      products.value = response;
    });

    const getTotal = () => {
      let totalTemp = 0;
      products.value.forEach((product) => {
        totalTemp += product.price * product.quantity;
      });
      return totalTemp.toFixed(2);
    };

    const deleteAllProductCart = (idProduct) => {
      deleteAllProductCartApi(idProduct);
      realoadCart.value = !realoadCart.value;
    };

    return {
      products,
      getTotal,
      deleteAllProductCart,
    };
  },
};
</script>

<style>
.title h1{
  text-align: center;
  padding-block-end: 5%;
  font-size: 3em;
}
</style>