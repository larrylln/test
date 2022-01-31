<template>
  <div class="container mt-7 v-cloak">
    <div class="row">
    <div class="col-12 text-center">
    <h2>{{title}}</h2>
    </div>
    <div class="col-12">
    <table class="table table-hover">
    <thead>
    <th>ID</th>
    <th>Email</th>
    <th>First Name</th>
    <th>Last Name</th>
    <th>Avatar</th>
    </thead>
    <tbody>
    <tr v-for="(user,index) in users" :key="index">
    <td>{{user.name}}</td>
    <td>{{user.name}}</td>
    <td></td>
    <td>f</td>
    <td>s</td>
    </tr>
    </tbody>
    </table>
    </div>
    </div>
  </div>
</template>

<script>
import { get } from 'axios';
export default {
  name: 'HelloWorld',
  data() {
    return {
      title:'User Information',
      user: []
    }
  },
    mounted() {
    let vm = this
    get('https://reqres.in/api/users/')
    .then(function(res) {
      vm.user = res.data.data
      console.log(vm.user)
    })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
