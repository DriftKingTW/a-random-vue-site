<template>
  <div class="user">
    <h1>This is an user page</h1>
    <button @click="getUser()">Click to fetch users from API</button>
    <p>User count: {{ userCount }}</p>
    <div v-if="users">
      <div v-for="(user, index) in users" :key="index">
        <p>Full Name: {{ user.name }}</p>
        <p>City: {{ user.city }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "user",
  data() {
    return {
      users: [],
    };
  },
  methods: {
    getUser() {
      axios
        .get("https://mocki.io/v1/d4867d8b-b5d5-4a48-a4ab-79131b5809b8")
        .then((data) => {
          console.log(data.data);
          this.users = [...this.users, ...data.data];
        });
    },
  },
  computed: {
    userCount() {
      return this.users.length;
    },
  },
  metaInfo: {
    title: "User Page",
    titleTemplate: "%s - A random vue site",
    meta: [
      { name: 'description', content: 'This is a page shows users info.' }
    ]
  },
};
</script>
