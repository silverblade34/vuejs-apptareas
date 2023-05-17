<template>
  <!-- <h1 class="titulo-1">Primer titulo H1</h1>
  <p>este es un texto normal</p>
-->
  <div class="app">
    <router-view />
  </div>
</template>

<script lang="ts" setup>
import SidebarComponent from './components/Sidebar/SidebarComponent.vue'
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;700&display=swap');

:root {
  --primary: #00747C;
  --secondary: #259ba3;
  --textohover: #adfaff;
  --grissuave: #a5a5a5;
  --grisfuerte: #4b4b4b;
  --sidebar-width: 300px;
  --white: #ffffff;
}

body {
  font-weight: bolder;
  font-family: 'Poppins', sans-serif;
  padding: 0;
  margin: 0;
}

button {
  cursor: pointer;
  appearance: none;
  border: none;
  outline: none;
  background: none;
}

h1 {
  color: var(--primary)
}

</style>
