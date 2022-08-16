<template>
  <div class="cart">
    <table class="table table-success table-striped"  >
      <thead>
        <tr>
          <th scope="col">#</th>
          <th scope="col">Name</th>
          <th scope="col">Price</th>
          <th scope="col">Qty</th>
          <th scope="col">Total</th>
        </tr>
      </thead>
      <tbody>
        <tr >
          <th scope="row">{{product.id}}</th>
          <td>{{ product.name }}</td>
          <td>$ {{ product.price }}</td>
          <td>{{ product.qty }}</td>
          <td>$ {{ product.total }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>


<script>


export default {
  name: 'CartView',
  data() {
    return {
      item: {},
      product: [],
      empty: "Your Cart is Empty!",
    }
  },
  mounted() {
    this.getData();
  },
  methods: {
    getData() {
      this.item = localStorage.getItem("storedData");
      // console.log(this.item.id);
      this.product = JSON.parse(this.item);
      console.log(this.product)
    }
  }
}
</script>