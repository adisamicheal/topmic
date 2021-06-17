<template>
<div>
  <nav class="flex justify-between p-10 desktop_nav">
      <div class="logo">
          Logo
      </div>
      <div class="nav">
        <ul class="flex justify-between">
            <li class="green text-bold"><router-link to="#">Home</router-link></li>
            <li class="ml-12 red text-bold"><router-link to="#">About</router-link></li>
            <li class="ml-12 blue text-bold"><router-link to="#">Contact</router-link></li>
            <li class="ml-12 purple text-bold"><router-link to="#">Staff</router-link></li>
        </ul>
      </div>
  </nav>
  <div class="mobile">
    <nav class="mobile_nav flex justify-between p-5">
        <div class="logo">
            Logo
        </div>
        <button class="navbar__button__mobile" :class="{'open' : isOpen}" @click="isOpen = !isOpen">
          <span></span>
          <span></span>
          <span></span>
        </button>
        <div class="nav__mobile" :class="{'open' : isOpen}">
          <ul class="m-0 list-unstyled nav__mobile__list">
              <li class="nav__mobile__list__item" @click="isOpen = !isOpen">
                  <a class="nav__mobile__link" href="#home">Home</a>
              </li>
              <li class="nav__mobile__list__item" @click="isOpen = !isOpen">
                  <a class="nav__mobile__link" href="#about">About</a>
              </li>
              <li class="nav__mobile__list__item" @click="isOpen = !isOpen">
                  <a class="nav__mobile__link" href="#services">Contact</a>
              </li>
              <li class="nav__mobile__list__item" @click="isOpen = !isOpen">
                  <a class="nav__mobile__link" href="#portfolio">Staff</a>
              </li>
          </ul>
      </div>
    <!-- </div> -->
    </nav>
  </div>
</div>
</template>

<script>
export default {
  name: "Navbar",
  data: () => ({
    isOpen: false,
  }),
};
</script>

<style scoped>
.mobile {
  display: none;
}
.navbar__button__mobile {
  /* display: none; */
  width: 48px;
  height: 40px;
  position: relative;
  transform: rotate(0deg);
  transition: .5s ease-in-out;
  cursor: pointer;
  background: transparent;
  border: none;
}
.navbar__button:focus,
.navbar__button__mobile:focus {
  outline: 0;
}
.navbar__button__mobile > span {
  display: block;
  position: absolute;
  height: 6px;
  width: 100%;
  background: #0066F5;
  border-radius: 9px;
  opacity: 1;
  left: 0;
  transform: rotate(0deg);
  transition: .25s ease-in-out;
}
.navbar__button__mobile > span:nth-child(1) {
  top: 0px;
  transform-origin: left center;
}
.navbar__button__mobile > span:nth-child(2) {
  top: 15px;
  transform-origin: left center;
}
.navbar__button__mobile > span:nth-child(3) {
  top: 30px;
  transform-origin: left center;
}
.navbar__button__mobile.open > span:nth-child(1) {
  transform: rotate(45deg);
  top: -3px;
  left: 10px;
}
.navbar__button__mobile.open > span:nth-child(2) {
  width: 0%;
  opacity: 0;
}
.navbar__button__mobile.open > span:nth-child(3) {
  transform: rotate(-45deg);
  top: 30px;
  left: 10px;
}
@media screen and (max-width: 767px) {
  .desktop_nav {
    display: none;
  }
  .mobile {
    display: block;
  }
  /* .navbar__button__mobile {
    display: block;
  } */
  .nav__mobile {
      /* display: block; */
      opacity: 0;
      max-height: 0px;
      background: #ffffff;
      z-index: 9000;
      transition: all .5s ease-in-out;
      padding: 2em;
      box-shadow: 0px 18px 20px #0066F5;
      position: absolute;
      top: 6em;
      width: 90vw;
      overflow: hidden;
  }
  .nav__mobile.open {
      opacity: 1;
      max-height: 70vh;
  }
  .nav__mobile__list {
      list-style: none;
  }
  .nav__mobile__list__item {
      padding: 1.5em 0;
      border-bottom: 1px solid #0066F5;
  }
  .nav__mobile__link {
      color: #0066F5;
      position: relative;
  }
  .nav__mobile__link:hover {
      text-decoration: none;
  }
}

</style>