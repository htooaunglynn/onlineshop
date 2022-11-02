<template>
  <div class="cart">
    <div class="have" v-if="product.length>0">
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
        <tbody v-for="(item,index) in product" :key="index">
          <tr >
            <th scope="row">
              <span>
                <button type="button" class="btn btn-outline-danger" @click="deleItem(index)">Del</button>
              </span>
              {{item.id}}
            </th>
            <td>{{ item.title }}</td>
            <td>$ {{ item.price }}</td>
            <td>
              <span>
                <button type="button" class="btn btn-outline-danger" @click="increaseBtn(index)">+</button>
              </span>
              {{ item.qty }}
              <span>
                <button type="button" class="btn btn-outline-danger" @click="decBtn(index)">-</button>
              </span>
            </td>
            <td >$ 
              {{ item.total }}
            </td>
          </tr>
        </tbody>
        
      </table>
    </div>
    <div class="without" v-else>
      <h1>Cart empty! </h1>
    </div>
  </div>
</template>


<script>


export default {
  name: 'CartView',
  data() {
    return {
      product: [],
      empty: "Your Cart is Empty!",
      alltotal: Number,
      price: 0,
      tot: 0,
    }
  },
  mounted() {
    this.getData();
    //this.total();
  },
  methods: {
    getData() {
      let coll;
      let item = localStorage.getItem('storageItem');
      if(item) {
        coll = JSON.parse(item);
      }
      this.product = coll;
    },
    increaseBtn(ids) {
      console.log(ids)
      let coll = localStorage.getItem("storageItem");
      let item = JSON.parse(coll);

      item[ids].qty ++;

      localStorage.setItem("storageItem", JSON.stringify(item)); 
      this.getData();
    },
    decBtn(ids) {
      console.log(ids)

      let coll = localStorage.getItem("storageItem");
      let item = JSON.parse(coll);

      if (item[ids].qty > 1) {
            item[ids].qty--;
        } else {
            let status = confirm("Are you sure delete?");

            if (status == true) {
                item.splice(ids,1);
            }
        }
      
      localStorage.setItem("storageItem", JSON.stringify(item)); 
      this.getData();
    },
    deleItem(ids) {
      let coll = localStorage.getItem("storageItem");
      let item = JSON.parse(coll);

      let status = confirm("Are you sure delete?");

        if (status == true) {
            item.splice(ids,1);
        }
      
      localStorage.setItem("storageItem", JSON.stringify(item)); 
      this.getData();
    },
    total() {
      let coll = localStorage.getItem("storageItem");
      let item = JSON.parse(coll);

      for(let ii of item) {
        this.alltotal +=  ii.total
      }
      console.log(this.alltotal)
    }
  }
}
</script>