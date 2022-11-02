<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col">
        <router-link to="/products" type="button" class="btn btn-outline-secondary mb-5">Back</router-link>
      </div>
      <div class="col">
          <router-link to="/cart" type="button" class="btn btn-outline-secondary mb-5"> <span>  item </span>View cart</router-link> 
      </div>
    </div>
  </div>
  
    <div class="container">
      <!-- <h1> {{ $route.params.id }} </h1> -->
      <div class="row">
        <div class="col-12">
          <div class="card mb-3">
            <div class="row g-0" >
              <div class="col-md-4" >
                <img :src="products.image" class="img-fluid rounded-start h-75 pt-5" alt="...">
              </div>
              <div class="col-md-8">
                <div class="card-body">
                  <h5 class="card-title fw-bolder pt-5">{{ products.title }}</h5>
                  <p class="card-text text-uppercase text-start pt-5" >{{ products.description }}</p> 
                  <h1 class="text-start pt-5">$ {{ products.price }}</h1>
                </div>
                <div class="input-group mb-3">
                  <button class="btn btn-outline-secondary" type="button" @click="incre">+</button>
                  <button class="btn btn-outline-secondary" type="button" @click="decre">-</button>
                  <input type="text" v-model="qty" class="form-control text-center" placeholder="Qty" aria-label="Recipient's username" aria-describedby="button-addon2">
                  <button class="btn btn-outline-secondary" type="button" id="button-addon2" @click="addtoCart(products)">Add to Cart</button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>  
    </div>
</template>

<script>

const axios = require('axios');
export default {
  name: 'ProductView',
  data() {
    return {
      products: [],
      qty: 1,
      total: 0
    }
  },
  mounted() {
    this.callAxio();
  },
  methods: {
    callAxio() {
      axios.get(`/products/${this.$route.params.id}`)
      .then(response => {
        // console.log(response)
        this.products = response.data
      })
    },
    addtoCart(products) {     
      let collection_item;
      let status = false;
      let cart = localStorage.getItem('storageItem');

      if(!cart) {
        collection_item = new Array;
      } else {
        collection_item = JSON.parse(cart);
      }

      products.qty = this.qty;
      //products.total = this.qty * products.price;

      for(let item of collection_item) {
        if(item.id == products.id) {
          item.qty += products.qty
          status = true;
          return false;
        }
      }

      if(status == false) {
        collection_item.push(products);
      }

      products.total = products.qty * products.price
      localStorage.setItem('storageItem', JSON.stringify(collection_item))
    },
    incre() {
      return ++this.qty;
    },
    decre() {
      return --this.qty;
    }
  }
}
</script>
<!-- 
<style>

img {
  width: fit-content;
  height: 30px;
}

</style> -->