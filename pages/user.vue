<template>
<div>
    <Users v-bind:users="users" />
</div>
</template>
<script>
import Users from "~/components/Users";
export default {
  name: 'UserPage',
  components: {
    Users,
  },
  data () {
    return {
      users: [],
    }
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