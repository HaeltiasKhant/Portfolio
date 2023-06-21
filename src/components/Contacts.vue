<template>
  <footer class="hidden">
    <div class="contactsContainer">
      <div class="email">
        <p>Contact me - </p>
        <h3>Khantthu1742002@gmail.com</h3>
      </div>

      <div class="socials">
        <h2>Follow me on - </h2>
        <div class="socialLogos">
          <img src="https://img.freepik.com/premium-vector/blue-social-media-logo_197792-1759.jpg" alt="fb">
          <img src="../assets/images/instagram.png" alt="instagram">
          <img src="../assets/images/telegram.png" alt="telegram">
        </div>

      </div>
    </div>
    
  </footer>
</template>

<script setup>
import { onMounted } from 'vue';
import scrollSmooth from '../composables/scrollSmooth';

onMounted(() => {
  scrollSmooth
})
</script>

<style scoped>
footer {
  margin-top: 200px;
  width: 100%;
  background-color: rgba(34, 13, 116, 0.84);
  padding: 0px 6%;
}

.contactsContainer {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}

.email {
  color: #fff;
}

.email p {
  font-size: 18px;
  margin-bottom: 10px;
  margin-top: 10px;
}

.email h3 {
  font-size: 30px;
  transition: all 0.5s;
  cursor: pointer;
  font-family: cursive;
}

.email h3:hover {
  opacity: 0.6;
}

.socials {
  display: flex;
  flex-direction: column;
}

.socials h2 {
 color: #fff;
}
.socialLogos {
  display: flex;
  flex-direction: column;
}

.socialLogos img {
  width: 60px;
  padding: 10px;
  user-select: none;
  cursor: pointer;
  transition: all 0.5s;
}

.socials img:hover {
  opacity: 0.5;
}

.hidden {
  opacity: 0;
  transform: translateY(60%);
  transition: all 1.2s;
}

.show {
  opacity: 1;
  transform: translateY(0);
}

@media screen and (max-width: 760px) {

  div.email {
    margin-left: -116px;
  }
  div.email h3 {
    font-size: 20px;
    text-align: start;
  }

  div.socialLogos {
    flex-direction: row;
    justify-content: center;
    flex-wrap: wrap;
  }

  div.socials h2 {
    margin-top: 10px;
    font-size: 18px;
  }

  div.socialLogos img {
    width: 16%;
    margin: 0px 10px;
  }
}

@media screen and (max-width: 400px) {
  div.email {
    margin-left: 0px;
  }

  div.socialLogos img {
    width: 20%;
  }
}
</style>