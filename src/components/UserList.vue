<template>
  <div v-if="users">
    <div v-for="(user, index) in users" :key="index">
      <p>Full Name: {{ user.name }}</p>
      <p>City: {{ user.city }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "UserList",
  props: {
    users: Array,
  },
};
</script>
