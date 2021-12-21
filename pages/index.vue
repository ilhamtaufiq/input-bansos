<template>
  <div class="bg-gray-100 mx-auto max-w-6xl bg-white py-20 px-12 lg:px-24 shadow-xl mb-24">
      <h1>Input Nama Penerima Bansos Covid-19</h1>
      <AddUserItem v-on:add-user-event="addUserItem"/>
  </div>
</template>
<script>
import Users from "~/components/Users";
import AddUserItem from "~/components/AddUser";
export default {
  name: 'App',
  components: {
    Users,
    AddUserItem
  },
  data () {
    return {
      users: [],
    }
  },
  methods: {
    addUserItem(newUser){
        this.users = [...this.users, newUser];
    },
  },
  watch: {
    users: {
      handler() {
        localStorage.setItem('users',JSON.stringify(this.users))
      },
      deep: true
    }
  },
  mounted() {
    if (localStorage.getItem("users")){
      this.users = JSON.parse(localStorage.getItem("users"))
    }
  }
}
</script>
