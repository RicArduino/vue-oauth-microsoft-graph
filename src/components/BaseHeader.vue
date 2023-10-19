<template>
  <div class="navbar">
    <router-link to="/" class="home-icon">
      🏠 Home
    </router-link>
    <button class="home-btn">
      <router-link to="/">HomePage</router-link>
    </button>
    <div class="login-status">🔒 Not yet logged-in</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      loggedIn: false,
    };
  },
  methods: {
    toggleLoginStatus() {
      this.loggedIn = !this.loggedIn;
    },
  },
};
</script>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 20px;
  background-color: #e9e9e9;
  border-bottom: 1px solid #c9c9c9;
  background-color: #29B883;
}

.home-icon {
  font-size: 20px;
  cursor: pointer;
}

.login-status {
  font-size: 16px;
  cursor: pointer;
}
.home-btn {
  margin-left: 10px;  /* ajoutez une marge pour l'espacement */
  background-color: #29B883;
  color: white;
  border: none;
  padding: 5px 10px;
  border-radius: 4px;
  cursor: pointer;
}

.home-btn:hover {
  background-color: #248d6c; /* une couleur plus foncée pour le survol */
}
</style>