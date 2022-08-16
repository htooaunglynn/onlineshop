<template>
  <!-- <div class="home"> -->
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <!-- <h1>This is home view</h1> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <!-- </div> -->
  <!-- carousel -->
  <div id="carouselExampleControls" class="carousel slide" data-bs-ride="carousel">
    <div class="carousel-inner">
      <div class="carousel-item active">
        <img src="../assets/bg1.jpg" class="d-block w-100">
      </div>
      <div class="carousel-item">
        <img src="../assets/bg2.jpg" class="d-block w-100">
      </div>
      <div class="carousel-item">
        <img src="../assets/bg3.jpg" class="d-block w-100" alt="...">
      </div>
    </div>
    <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleControls" data-bs-slide="prev">
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Previous</span>
    </button>
    <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleControls" data-bs-slide="next">
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Next</span>
    </button>
  </div>
  <!-- carousel -->
  <h1 class='my-4'>Products</h1>
  <hr class="mx-5">
  <!-- product  -->
   <!-- <div class="container">
    <div class="row">
      <div class="col-12 col-lg-3" v-for="(item, index) in products" :key="index">
        <div class="card">
          <img :src="item.image" class="card-img-top w-50 h-50" alt="...">
          <div class="card-body">
            <p class="card-text">{{item.name}}</p>
          </div>
        </div>
      </div>
    </div>
  </div> -->
  <!-- product  -->
  
   <!-- behavior  -->
   <div class="container">
    <div class="row justify-content-center">
      
        <!-- j  -->
        <div class="col-12 col-xl-7 col-lg-7 col-md-6 col-sm-12">
          <ul class="nav nav-tabs" id="myTab" role="tablist">
            <li class="nav-item" role="presentation">
              <button class="nav-link active" id="home-tab" data-bs-toggle="tab" data-bs-target="#home-tab-pane" type="button" role="tab" aria-controls="home-tab-pane" aria-selected="true">ALL</button>
            </li>
            <li class="nav-item" role="presentation">
              <button class="nav-link" id="profile-tab" data-bs-toggle="tab" data-bs-target="#profile-tab-pane" type="button" role="tab" aria-controls="profile-tab-pane" aria-selected="false">Men's clothing</button>
            </li>
            <li class="nav-item" role="presentation">
              <button class="nav-link" id="contact-tab" data-bs-toggle="tab" data-bs-target="#contact-tab-pane" type="button" role="tab" aria-controls="contact-tab-pane" aria-selected="false">Jewelery</button>
            </li>
            <li class="nav-item" role="presentation">
              <button class="nav-link" id="disabled-tab" data-bs-toggle="tab" data-bs-target="#disabled-tab-pane" type="button" role="tab" aria-controls="disabled-tab-pane" aria-selected="false">Electronics</button>
            </li>
            <li class="nav-item" role="presentation">
              <button class="nav-link" id="messages-tab" data-bs-toggle="tab" data-bs-target="#messages" type="button" role="tab" aria-controls="messages" aria-selected="false">Women's clothing</button>
            </li>
          </ul>
        </div>
        <!-- ---  -->
        <div class="col-12 mt-3">
          <div class="tab-content" id="myTabContent">
            <!-- all  -->
            <div class="tab-pane fade show active" id="home-tab-pane" role="tabpanel" aria-labelledby="home-tab" tabindex="0">
              <div class="row g-3">
                <div class="col-12 col-xxl-2 col-xl-3 col-lg-4 col-md-6 col-sm-12" v-for="(item, index) in products" :key="index">
                  <div class="card my-5">
                    <img :src="item.image" class="card-img-top" alt="...">
                    <div class="card-body">
                      <h5 class="card-title">{{ item.title }}</h5>
                      <p class="card-text">{{ item.description }}</p>
                      <router-link :to="`/product/${item.id}`" class="btn btn-primary">Details</router-link>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <!-- all  -->
            <!-- Men's clothing  -->
            <div class="tab-pane fade" id="profile-tab-pane" role="tabpanel" aria-labelledby="profile-tab" tabindex="0">
              <div class="row g-3" >
                <div class="col-12 col-xxl-2 col-xl-3 col-lg-4 col-md-6 col-sm-12" v-for="(item, index) in products" :key="index">
                  <div class="card my-5" v-if="item.category == menClo">
                    <img :src="item.image" class="card-img-top" alt="...">
                    <div class="card-body">
                      <h5 class="card-title">{{ item.title }}</h5>
                      <p class="card-text">{{ item.description }}</p>
                      <router-link :to="`/product/${item.id}`" class="btn btn-primary">Details</router-link>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <!-- Men's clothing  -->
            <!-- jewelery  -->
            <div class="tab-pane fade" id="contact-tab-pane" role="tabpanel" aria-labelledby="contact-tab" tabindex="0">
              <div class="row g-3" >
                <div class="col-12 col-xxl-2 col-xl-3 col-lg-4 col-md-6 col-sm-12" v-for="(item, index) in products" :key="index">
                  <div class="card my-5" v-if="item.category == jew">
                    <img :src="item.image" class="card-img-top" alt="...">
                    <div class="card-body">
                      <h5 class="card-title">{{ item.title }}</h5>
                      <p class="card-text">{{ item.description }}</p>
                      <router-link :to="`/product/${item.id}`" class="btn btn-primary">Details</router-link>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <!-- jewelery  -->
            <!-- electronics  -->
            <div class="tab-pane fade" id="disabled-tab-pane" role="tabpanel" aria-labelledby="disabled-tab" tabindex="0">
              <div class="row g-3" >
                <div class="col-12 col-xxl-2 col-xl-3 col-lg-4 col-md-6 col-sm-12" v-for="(item, index) in products" :key="index">
                  <div class="card my-5" v-if="item.category == ele">
                    <img :src="item.image" class="card-img-top" alt="...">
                    <div class="card-body">
                      <h5 class="card-title">{{ item.title }}</h5>
                      <p class="card-text">{{ item.description }}</p>
                      <router-link :to="`/product/${item.id}`" class="btn btn-primary">Details</router-link>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <!-- electronics  -->
            <!-- women's clothing  -->
            <div class="tab-pane fade" id="messages" role="tabpanel" aria-labelledby="messages-tab" tabindex="0">
              <div class="row g-3" >
                <div class="col-12 col-xxl-2 col-xl-3 col-lg-4 col-md-6 col-sm-12" v-for="(item, index) in products" :key="index">
                  <div class="card my-5" v-if="item.category == woClo">
                    <img :src="item.image" class="card-img-top" alt="...">
                    <div class="card-body">
                      <h5 class="card-title">{{ item.title }}</h5>
                      <p class="card-text">{{ item.description }}</p>
                      <router-link :to="`/product/${item.id}`" class="btn btn-primary">Details</router-link>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <!-- women's clothing  -->
          </div>
        </div>
        <!-- j  -->
      
    </div>
   </div>
   <!-- behavior  -->
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
const axios = require('axios');
export default {
  name: 'HomeView',
  data() {
    return {
      products: [],
      menClo: "men's clothing",
      jew: "jewelery",
      ele: "electronics",
      woClo: "women's clothing",
    }
  },
  mounted() {
    axios.get('/products')
    .then(response => {
      console.log(response)
      this.products = response.data
    })
  }
}
</script>

<style>
.carousel-item img {
    height: 80vh;
    object-fit: cover;
}
</style>
