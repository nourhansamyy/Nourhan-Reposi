<template>
    <div class="row">
      <div class="col-md-12">
        <div class="card">
  <button @click= "CreateProduct()">  Create Me!</button>s
          <table class="table table-bordered table-inverse">

      <thead>
        <tr>
          <th>#</th>
          <th> Name</th>
          <th> Price</th>
          <th> Created AT</th>
          <th> Updated AT</th>
          <th> Actions </th>
          <th> sellername </th>

        </tr>
      </thead>
      <tbody>
        <tr v-for= "product in ProductsArray.data">=

          <td> {{product.name}} </td>
          <td> {{product.price}} </td>
          <td> {{product.createdAt}} </td>
          <td> {{product.updatedAt}} </td>
          <td>  <img src="static/img/bin image." v-on:mouseover="hovered()" />  </td>
          <td> Nourhan Samy </td>



        </tr>
      </tbody>

    </table>
        </div>
      </div>
      <input type="text" v-model= "product.name"> Name <br>
      <input type="text" v-model= "product.price"> Price <br>
      <input type="text" v-model= "product.id"> IDUPDATE <br>
 <button @click= "UpdateMe()">  Update Me!</button>

<br>
<br>
  <button @click= "DeleteMe()">  Delete Me!</button> <input type="text" v-model= "product.id"> ID <br>
  <br>
  <br>
  <button @click= "Search()">   Search!</button> <input type="text" v-model= "product.id"> ID <br>
    </div>
</template>
<script>

import axios from 'axios'
import PaperTable from 'components/UIComponents/PaperTable.vue'
const tableColumns = ['Id', 'Name', 'Price', 'CreatedAt', 'UpdatedAt', 'SellerName', 'Action', '']
const tableData = [{

},
{

}]
export default {
  components: {
    PaperTable
  },
  data () {
    return {
      product: {
        id: '',
        name: '',
        price: '',
        createdat: '',
        updatedat: ''
      },
      ProductsArray: []

    }
  },
  mounted () {
    axios.get('http://localhost:3000/api/product/getProducts')
    .then((response) => {
      console.log(response.data)
      this.ProductsArray = response.data
    })
  },
  methods: {
    CreateProduct () {
      axios.post('http://localhost:3000/api/product/createProduct', {
        name: 'dog',
        price: 5000
      })
    .then((response) => {
      console.log(response)
    })
    .catch((error) => {
      console.log(error)
    })
    },
    DeleteMe () {
      axios.delete('http://localhost:3000/api/product/deleteProduct' + '/' + this.product.id)
  .then((response) => {
    console.log(response)
  })
  .catch((error) => {
    console.log(error)
  })
    },
    UpdateMe () {
      axios.patch('http://localhost:3000/api/product/updateProduct' + '/' + this.product.id, {
        name: this.product.name,
        price: this.product.price
      })
    .then((response) => {
      console.log(response)
    })
    .catch((error) => {
      console.log(error)
    })
    }
  }
}

</script>
<style>

</style>
