<template>
  <div class="myProjects">
    <h1 class="hidden">Projects I've done</h1>
    <div class="projectsContainer">
      <div v-for="projectInfo in projectInfos" :key="projectInfo.id" class="project hidden">
        <a :href="projectInfo.url" class="hidden">
          <img :src="projectInfo.img" :alt="projectInfo.name">
          <p>{{ projectInfo.name }}</p>
        </a>
      </div>
    </div>
  </div>
</template>

<script setup>
import { onMounted, ref } from 'vue';
import pIf from '../data/projectsInfos.json'
import scrollSmooth from '../composables/scrollSmooth';

const projectInfos = ref(pIf)

onMounted(() => {
  scrollSmooth()
})
</script>

<style scoped>
.myProjects {
  max-width: 1000px;
  margin: 0 auto;
  min-height: 100vh;
  display: grid;
  align-content: center;
  padding: 5px;
}
.projectsContainer {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  align-content: start;
  position: relative;
}

.project {
  width: 90%;
  background-color: #fff;
  padding: 10px;
  border-radius: 6px;
  box-shadow: 10px 10px 8px 10px #2a2929;
}

.project:nth-child(3) {
  transition-delay: 200ms;
}

.project:nth-child(4) {
  transition-delay: 400ms;
}

.project:nth-child(5) {
  transition-delay: 600ms;
}

.project img {
  width: 100%;
}

.project p {
  color: rgb(228, 76, 208);
  text-align: center;
  margin-top: 5px;
  font-size: 20px;
  text-align: start;
}

.hidden {
  opacity: 0;
  transform: translateX(-80%);
  transition: all 1.4s;
}

.show {
  opacity: 1;
  transform: translateX(0);
}

h1 {
  text-align: start;
  color: #fff;
  font-size: 40px;
  margin-bottom: 20px;
}

.project a {
  text-decoration: none;
}

@media screen and (max-width: 760px) {
  div.projectsContainer {
    grid-template-columns: repeat(2, 1fr);
    grid-gap: 20px;
  }

  h1 {
    font-size: 26px;
    position: static;
    margin-bottom: 20px;
  }

  div.project {
    width: 94%;
  }

  div.project p {
    font-size: 18px;
  }
}

@media screen and (max-width: 390px) {
  div.project p {
    font-size: 16px;
  }

  div.project {
    width: 100%;
  }

  div.projectsContainer {
    grid-gap: 16px;
  }
}
</style>

