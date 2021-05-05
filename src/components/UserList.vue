<template>
  <div class="user-list" v-if="users">
    <div class="user-card" v-for="(user, index) in users" :key="index">
      <img src="@/assets/default-profile.png" alt="" />
      <p class="text-name">{{ user.name }}</p>
      <p class="text-location">{{ user.city }}</p>
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

<style scoped lang="scss">
@import "@/assets/master.scss";

.user-list {
  display: flex;
  justify-content: center;
  gap: 1.5rem;
  padding: 0.5rem;

  img {
    width: 100%;
  }
}

.user-card {
  min-width: 20ch;
  max-width: 25ch;
  box-shadow: 0 4px 8px 0 $light-gray;
  transition: 0.3s;
  border-radius: 5px;
  text-align: center;

  &:hover {
    box-shadow: 0 8px 16px 0 $light-gray;
  }
}

.text-name {
  color: $primary-dark;
  font-weight: bold;
  font-size: 1.2rem;
}

.text-location {
  color: $primary;
  font-weight: 100;
}

@media (max-width: $desktop) {
  .user-list {
    flex-wrap: wrap;
  }
}

</style>