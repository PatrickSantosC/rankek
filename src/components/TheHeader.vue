<template>
  <header>
    <nav>
      <router-link to="/" class="logo">
        <img src="../assets/ranek.svg" alt="" />
      </router-link>
      <router-link to="/usuario" v-if="$store.state.login" class="btn">
        {{ nome }}
      </router-link>
      <router-link v-else to="/login" class="btn">Vender / Login</router-link>
    </nav>
  </header>
</template>

<script>
export default {
  name: "TheHeader",
  computed: {
    nome() {
      return this.$store.state.usuario.nome.replace(/ .*/, "");
    },
  },
};
</script>

<style scoped>
nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 15px 20px;
  box-shadow: 0 2px 4px rgba(30, 60, 90, 0.1);
}

.logo {
  padding: 10px 0;
}

.logo img {
  width: 90px;
}

.btn {
  text-transform: capitalize;
}
</style>
