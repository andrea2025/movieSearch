<template>
  <div>
    <form v-on:submit.prevent="submitForm">
      <div class="form__item">
        <label for="name">Full Name</label>
        <input type="name" name="name" id="" v-model="newUser.fullName">
      </div>
      <div class="form__item">
        <label for="email">Email Address</label>
        <input type="email" name="email" id="" v-model="newUser.email">
      </div>
      <div class="form__item">
        <label for="phone">Phone Number</label>
        <input type="tel" name="phone" id="" v-model="newUser.phone">
      </div>
      <button type="submit">Send</button>
    </form>

    <table>
      <thead>
        <tr>
          <th>Full Name</th>
          <th>Email Address</th>
          <th>Phone Number</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(user, index) in allusers" v-bind:key="index">
          <td>{{ user.fullName }}</td>
          <td>{{ user.email }}</td>
          <td>{{ user.phone }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script>
export default {
  name: 'ContactForm',
  data() {
    return {
      newUser: {
        fullName: '',
        email: '',
        phone: ''
      },
      allusers: []
    }
  },
  methods: {
    submitForm() {
      this.allusers.push(this.newUser)
      this.clearForm()
    },
    clearForm() {
      this.newUser = {
        fullName: '',
        email: '',
        phone: ''
      }
    }
  }
}
</script>

<style>
form {
  max-width: 400px;
  background: pink;
  padding: 2rem;
  border-radius: 8px;
  margin: 40px auto;
}
.form__item {
  display: block;
  max-width: 100%;
  margin-bottom: 1rem;
}
.form__item > label {
  display: block;
}
.form__item > input {
  padding: 1rem;
  font-size: 18px;
  border-radius: 8px;
  color: pink;
  background: #fff;
  border: 2px solid pink;
  width: 90%;
}
button {
  padding: 1rem 3rem;
  background: black;
  color: #fff;
}
table {
  border: 1px solid black;
  width: 100%;
}
td, th {
  border: 1px solid #3333;
  padding: 1rem;
}
tr:nth-child(even) {
background: #dbdbdb;
}
</style>
