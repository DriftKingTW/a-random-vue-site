<template>
  <div class="user">
    <h1>This is an user page</h1>
    <a class="btn effect" @click.prevent="getUser()" data-sm-link-text="CLICK"
      ><span>Get Data</span></a
    >
    <p>User count: {{ userCount }}</p>
    <UserList :users="users"></UserList>
  </div>
</template>

<script>
import axios from "axios";
import UserList from "@/components/UserList";

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
          this.users = [...data.data];
        });
    },
  },
  computed: {
    userCount() {
      return this.users.length;
    },
  },
  components: {
    UserList,
  },
  metaInfo: {
    title: "User Page",
    titleTemplate: "%s - A random vue site",
    meta: [
      { name: "description", content: "This is a page shows users info." },
    ],
  },
};
</script>
