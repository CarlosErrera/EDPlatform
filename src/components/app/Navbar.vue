<template>
  <nav class="navbar blue lighten-1">
    <div class="nav-wrapper">
      <router-link to="/">
        <img class="logo" src="@/assets/images/logo.png" alt="logo" />
      </router-link>
      <ul class="navbar-content black-text">
        <li>
          <router-link class="navbar-li" to="/ege">ЕГЭ</router-link>
        </li>
        <li>
          <router-link class="navbar-li" to="/oge">ОГЭ</router-link>
        </li>
        <li class="profile">
          <router-link class="white-text navbar-li" to="/user/statistics"
            >Личный кабинет</router-link>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: "navbar",
  data: () => ({
    dropdown: null
  }),
  methods: {
    async logout() {
      this.$store.dispatch("logout");
      this.$router.push("/authorization?message=logout");
    }
  }
};
</script>

<style>
.logo {
  width: 150px;
  height: 50px;
}

.nav-wrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.nav-wrapper a {
  height: 60px;
}

.navbar-content {
  margin: auto;
  width: 85%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.profile {
  margin-left: auto;
}

.navbar-li {
  font-size: 18px;
  font-weight: 500;
}
</style>
