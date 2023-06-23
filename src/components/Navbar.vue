<template>
  <nav>
    <div class="myName">
      <span>K</span>
      <p>HANT</p>
    </div>
    <ul class="menu">
      <li @click="scrollTo(1700)">About</li>
      <li @click="scrollTo(2000)">Contacts</li>
      <li @click="scrollTo()">Portfolio</li>
    </ul>
    <div @click="toggleMenuItems" class="hamburgerMenu">
      <div id="line1"></div>
      <div id="line2"></div>
      <div id="line3"></div>
    </div>
    <transition>
      <div v-show="showMenuItems" class="menuItems">
        <ul>
          <li @click="scrollTo(1480)">About</li>
          <li @click="scrollTo(2200)">Contacts</li>
          <li>Portfolio</li>
        </ul>
      </div>
    </transition>
  </nav>
</template>

<script setup>
import { ref } from 'vue';


const showMenuItems = ref(false)

const toggleMenuItems = () => {
  const hamburgerMenuTag = document.getElementsByClassName('hamburgerMenu')[0]
  const hamburgerMenuLine1 = document.getElementById('line1')
  const hamburgerMenuLine2 = document.getElementById('line2')
  const hamburgerMenuLine3 = document.getElementById('line3')
  if (hamburgerMenuTag.classList.contains('isOpened')) {
    hamburgerMenuTag.classList.remove('isOpened')
    hamburgerMenuLine2.classList.remove('hideLine2')
    hamburgerMenuLine1.classList.remove('cross1')
    hamburgerMenuLine3.classList.remove('cross2')
  } else {
    hamburgerMenuLine2.classList.add('hideLine2')
    hamburgerMenuTag.classList.add('isOpened')
    hamburgerMenuLine1.classList.add('cross1')
    hamburgerMenuLine3.classList.add('cross2')
  }
  showMenuItems.value = !showMenuItems.value
}

const scrollTo = (y) => {
  window.scrollTo({
    top: y,
    behavior: 'smooth'
  })
}


</script>

<style scoped>
nav {
  display: flex;
  justify-content: space-between;
  padding: 20px 0px;
  position: relative;
}

.myName {
  color: #fff;
}

.myName span {
  display: inline;
  font-weight: 900;
  font-size: 40px;
}

.myName p {
  display: inline;
  font-size: 30px;
  padding: 2px;
}

.menu {
  display: inline-block;
}

.menu li {
  display: inline-block;
  list-style: none;
  margin: 10px 30px;
  padding: 4px;
  color: #fff;
  cursor: pointer;
  user-select: none;
  transition: all 0.2s ease-in-out;
  border-bottom: 0px transparent;
  font-size: 24px;
}

.menu li:hover {
  border-bottom: 3px solid #fff;
}

.hamburgerMenu {
  display: none;
}

.hamburgerMenu #line1,
#line2,
#line3 {
  width: 36px;
  height: 4px;
  background-color: aqua;
  margin: 4px 0px;
  transition: all 0.8s;
}

.menuItems {
  display: none;
}

.menuItems ul {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 0;
  padding: 0;
  color: aqua;
}

.menuItems ul li {
  display: block;
  padding: 20px 22px;
  user-select: none;
  cursor: pointer;
  font-size: 18px;
}

.menuItems ul li:nth-child(2) {
  border-bottom: 1px solid rgb(44, 44, 44);
  border-top: 1px solid rgb(44, 44, 44);
}

.hideLine2 {
  opacity: 0;
}

.cross1 {
  transform: rotate(45deg) translate(4px, 13px);
}

.cross2 {
  transform: rotate(-45deg) translate(4px, -13px);
}

/* we will explain what these classes do next! */
.v-enter-active,
.v-leave-active {
  transition: opacity 0.8s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}

@media screen and (max-width: 760px) {
  ul.menu {
    display: none;
  }

  div.hamburgerMenu {
    display: flex;
    flex-direction: column;
  }

  div.menuItems {
    display: block;
    background-color: rgb(54, 15, 182);
    border-radius: 10%;
    border: 2px solid rgb(44, 44, 44);
    position: absolute;
    top: 80%;
    right: 0;
  }

}

@media screen and (max-width: 400px) {
  div.myName span {
    font-size: 30px;
  }

  div.myName p {
    font-size: 18px;
  }
}
</style>
