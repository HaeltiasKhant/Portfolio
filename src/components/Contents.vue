<template>
  <div class="textBox">
    <p class="hidden normalFont">I'M</p>
    <h1 class="hidden largeFont">KHANT</h1>
    <h3 class="hidden normalFont">I AM CURRENTLY A JUNIOR WEB DEVEOPER</h3>

    <div class="projects hidden">
      <h3 @click="scrollTo">My Projects <span>&#8594;</span></h3>
      <p>You can explore my projects here.</p>
    </div>
  </div>
</template>

<script setup>
import { onMounted } from 'vue';
import scrollSmooth from '../composables/scrollSmooth'

const emits = defineEmits(['toView'])

const scrollTo = () => {
  window.scrollTo({
    top: 700,
    behavior: 'smooth'
  })
}
 

onMounted(() => {
  scrollSmooth()
})
</script>
 
<style scoped>
.textBox {
  color: #fff;
  position: absolute;
  bottom: 10%;
}

.textBox p {
  font-size: 50px;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
}

.textBox h1 {
  font-size: 160px;
  margin-left: -10px;
  line-height: 160px;
  font-weight: 800;
  color: transparent;
  -webkit-text-stroke: 0.6px #fff;
  background: url(../assets/images/back.png);
  -webkit-background-clip: text;
  background-position: 0 0;
  animation: back 20s linear infinite;
}

@keyframes back {
  100% {
    background-position: 2000px 0;
  }
}

.textBox h3 {
  font-size: 40px;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
}

.projects {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  margin-top: 40px;
}

.projects h3 {
  user-select: none;
  cursor: pointer;
  color: #fff;
  border: 1px solid #fff;
  padding: 8px 10px;
  margin-right: 5px;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  font-size: 26px;
}

.projects a:hover {
  background-color: #fff;
  color: black;
}

.projects p {
  font-size: 26px;
}

.hidden {
  opacity: 0;
  transform: translateY(100%);
  transition: all 1.5s;
}

.show {
  opacity: 1;
  transform: translateY(0);
}

@media screen and (max-width: 760px) {

  div.textBox {
    bottom: 20%;
  }
  div.textBox p {
    font-size: 20px;
  }

  div.textBox h3 {
    font-size: 20px;
  }

  div.textBox h1 {
    margin-left: 0px;
    font-size: 94px;
    line-height: 90%;
  }

  div.projects p {
    margin-top: 10px;
  }
}

@media screen and (max-width: 300px) {
  div.textBox h1 {
    font-size: 70px;
  }

  div.textBox h3 {
    font-size: 18px;
  }

  div.projects p {
    font-size: 18px;
  }

  div.projects h3 {
    font-size: 20px;
  }
}
</style>