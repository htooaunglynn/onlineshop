<template>
  <!-- <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/product">Product</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link to="/contact">Contact</router-link> 
  </nav> -->
 

  <!-- nav  -->
  <nav class="navbar navbar-expand-lg bg-light">
    <div class="container">
      <a class="navbar-brand custom-font fs-3 hoverColor" href="#">Fake Store</a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse justify-content-end" id="navbarNav">
        <ul class="navbar-nav">
          <li class="nav-item me-3 fs-4 fw-bold">
            <!-- <a  href="/"> -->
              <router-link to="/" class="nav-link active hoverColor" aria-current="page">Home</router-link>
            <!-- </a> -->
          </li>
          <li class="nav-item me-3 fs-4 fw-bold">
            <!-- <a class="nav-link" href="#"> -->
              <router-link to="/products" class="nav-link hoverColor">Product</router-link>
            <!-- </a> -->
          </li>
          <li class="nav-item me-3 fs-4 fw-bold">
            <!-- <a class="nav-link" href="#"> -->
              <router-link to="/cart" class="nav-link hoverColor">Cart</router-link>
            <!-- </a> -->
          </li>
          
        </ul>
      </div>
    </div>
  </nav>
  <!-- nav  -->
   <router-view/>
   <!-- <footer>
    <p> Copyright &copy; 2022 | Design By &hearts; Htoo Aung Lynn </p>
   </footer> -->
</template>

<script>

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

@import url('https://fonts.googleapis.com/css2?family=Rubik+Marker+Hatch&display=swap');

.custom-font {
  font-family: 'Rubik Marker Hatch', cursive;
}

* {
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
}

.hoverColor:hover {
  color: aqua !important;
}
/* nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}  */
footer {
  width: 100%;
  height: 50px;
  background-color: black;
}
footer p{
  padding-top: 15px;
}
</style>
