<template>
  <div class="products container my-5">
    <div class="row">
      <div class="col-12 col-xxl-2 col-xl-3 col-lg-4 col-md-6 col-sm-12 my-4" v-for="(item, index) in products" :key="index">
       <div class="card">
          <img :src="item.image" class="card-img-top" :alt="item.title">
          <div class="card-body">
            <h5 class="card-title fs-4 fw-bold" v-html="capitalize(item.title)"> </h5>
            
              <router-link :to="`/product/${item.id}`" class="btn btn-primary">Details</router-link>
            
          </div>
        </div>
      </div>
    </div>
    
  </div>

</template>

<script>

const axios = require('axios');
export default {
  name: 'ProductsView',
  data() {
    return {
      products: {},
    }
  },
  mounted() {
    axios.get('/products')
    .then(response => {
      // console.log(response)
      this.products = response.data
    })
  },
  methods: {
    capitalize(value){
        return value.replace(/(?:^|\s|-)\S/g, x => x.toUpperCase());
    }
  }
}
</script>

<style>
a {
  text-decoration: none;
  color: wheat;
}
</style>