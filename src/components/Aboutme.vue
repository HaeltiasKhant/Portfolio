<template>
  <div class="cardContainer">
    <div class="card1 hidden">
      <h1>About me</h1>
      <img
        src="https://e7.pngegg.com/pngimages/799/987/png-clipart-computer-icons-avatar-icon-design-avatar-heroes-computer-wallpaper.png"
        alt="">
      <p>"My name is Khant Thu and I have been learning web development almost six months now.I was always interested in
        games and web designs since I was a kid and now that I am learning it, I am really starting enjoying it.I want
        to cover as many as skills I can to become a proficient web developer.And I am really excited to write projects as a
        team and share experiences so if you need a team player for your projects, you can count on me!"
      </p>
    </div>
    <div class="card2">
      <h1 class="hidden">My skills</h1>
      <div class="skillLogos hidden">
        <img src="https://img.freepik.com/free-icon/html-5_318-674234.jpg" alt="">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/62/CSS3_logo.svg/1200px-CSS3_logo.svg.png"
          alt="">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6a/JavaScript-logo.png/800px-JavaScript-logo.png"
          alt="">
        <img
          src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Vue.js_Logo_2.svg/1200px-Vue.js_Logo_2.svg.png"
          alt="">
        <img
          src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Python-logo-notext.svg/1200px-Python-logo-notext.svg.png"
          alt="">
        <img src="https://www.datocms-assets.com/45470/1631795624-logo-django.png" alt="">
      </div>
    </div>
  </div>
</template>

<script setup>
import { onMounted } from 'vue';
import scrollSmooth from '../composables/scrollSmooth';

onMounted(() => {
  scrollSmooth()
})
</script>

<style scoped>
.cardContainer {
  max-width: 760px;
  height: 100vh;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.card1 {
  background-color: transparent;
  width: 50%;
  padding: 20px;
  border-radius: 10px;
  border: 1px solid gray;
}

.card1 h1 {
  margin-bottom: 10px;
  color: #fff;
  font-size: 40px;
}

.card1 img {
  width: 100%;
}

.card1 p {
  font-style: italic;
  color: #fff;
  font-size: 20px;
  font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
}

.card2 {
  width: 40%;
}

.card2 h1 {
  color: #fff;
  font-size: 40px;
}

.skillLogos img {
  width: 20%;
  margin: 20px;
}

.hidden {
  opacity: 0;
  transform: translateX(-80%);
  transition: all 1.5s;
}

.show {
  opacity: 1;
  transform: translateY(0);
}

@media screen and (max-width: 760px) {
  div.cardContainer {
    flex-wrap: wrap;
    padding: 5px;
  }

  div.card1 {
    width: 100%;
  }

  div.card2 {
    width: 100%;
  }

  div.card1 h1 {
    font-size: 26px;
  }

  div.card1 img {
    width: 100%;
  }

  div.card1 p {
    font-size: 20px;
  }

  div.skillLogos {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    margin-top: -10px;
  }

  div.card2 h1 {
    font-size: 20px;
    text-align: center;
    margin-top: 10px;
  }
  div.skillLogos img {
    width: 50%;
  }
}

@media screen and (max-width: 390px) {
  div.card1 p {
    font-size: 20px;
  }

  div.skillLogos img {
    width: 40%;
  }
}
</style>