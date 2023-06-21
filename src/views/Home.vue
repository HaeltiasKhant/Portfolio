<template>
  <div class="main">
    <Navbar />
    <Contents  />
  </div>
  <Myprojects id="myPs"/>
  <Aboutme id="abtMe" />
  <Contacts />
</template>

<script setup>
import Navbar from '../components/Navbar.vue';
import Contents from '../components/Contents.vue'
import Myprojects from '../components/Myprojects.vue';
import Aboutme from '../components/Aboutme.vue';
import { onMounted } from 'vue';
import Contacts from '../components/Contacts.vue';

</script>

<style scoped>
.main {
  max-width: 1200px;
  margin: 0 auto;
  position: relative;
  min-height: 100vh;
  padding: 10px;
}

@media screen and (max-width: 760px) {
  div.main {
    width: 100vw;
    padding: 10px;
  }
}
</style>