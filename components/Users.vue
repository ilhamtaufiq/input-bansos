<template>
    <div>
        <h2>Nama - Nama Penerima Bantuan Sosial (Bansos)</h2>
        <div v-bind:key="user.id" v-for="user in users">
            <UserItem v-bind:user="user"  />
        </div>
        <div v-if="!users.length">
            <p>No Users to Read!!</p>
        </div>
    </div>
</template>

<script>
    import UserItem from "./UserItem";
    export default {
        nama: "Users",
        props: ["users"],
        components: {
            UserItem
        },
        methods: {

        }
    }
</script>

<style scoped>
</style>