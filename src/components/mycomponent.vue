<template>
  <div>
    <form v-on:submit.prevent="submitForm">
      <div class="form__item">
        <label for="name">Name</label>
        <input type="name" name="name" id="" v-model="newProduct.name">
      </div>
      <div class="form__item">
        <label for="price">Price</label>
        <input type="number" name="price" id="" v-model.number="newProduct.price">
      </div>
      <div class="form__item">
        <label for="quantity">Quantity</label>
        <input type="number" name="quantity" id="" v-model.number="newProduct.quantity">
      </div>
      <p>Subtotal: {{ subTotal }}</p>
      <button type="submit">Add to List</button>
    </form>
    <table>
      <thead>
        <tr>
          <th>Name</th>
          <th>Price</th>
          <th>Qanutity</th>
          <th>SubTotal</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(item, index) in list" v-bind:key="index">
          <td>{{ item.name }}</td>
          <td>{{ item.price }}</td>
          <td>{{ item.quantity }}</td>
          <td>{{ item.price * item.quantity }}</td>
        </tr>
      </tbody>
    </table>
    <h2>
      Total Price: {{ totalPrice }}
    </h2>
  </div>
</template>
<script>
  export default {
    name: 'ComputedComponent',
    data() {
      return {
        list: [
          {
            name: 'shoes',
            price: 20000,
            quantity: 1,
          },
          {
            name: 'shirts',
            price: 5000,
            quantity: 1,
          }
        ],
        newProduct: {
          name: '',
          price: 0,
          quantity: 1
        }
      }
    },
    methods: {
      submitForm() {
        this.list.push(this.newProduct)
        this.newProduct = {
          name: '',
          price: 0,
          quantity: 1,
        }
      }
    },
    computed: {
      totalPrice() {
        let total = 0;
        this.list.map(item => total = total + (item.price * item.quantity))
        return total;
      },
      subTotal() {
        return this.newProduct.price * this.newProduct.quantity
      }
    }
  }
</script>
<style scoped>

</style>