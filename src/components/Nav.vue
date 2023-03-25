<template>
  <div class="navbar">
    <img class="logo" src="../assets/logo.jpg" />
    <div class="nav-container">
      <b-nav>
        <b-nav-item active href="#homeSlider">Home</b-nav-item>
        <b-nav-item href="#makeup-section">Makeup</b-nav-item>
        <b-nav-item href="#skincare-section">Skin care</b-nav-item>
        <b-nav-item href="#feedback-section">Feedback</b-nav-item>
        <b-nav-item @click="openDialog" class="login">Login</b-nav-item>
        <b-nav-item  @click="menuClose" class="closeMenu">close</b-nav-item>
        <Login v-if="dialog" @close-dialog="closeDialog" />
      </b-nav>
    </div>
    <div @click="openDialog"><img class="login" src="../assets/login.svg" /></div>
    <div @click="menuOpen" class="menu-toggler"><img src="../assets/menu-btn.svg" /></div>
  </div>
</template>
<script>
import Login from "./dialogs/Login";
import $ from 'jquery'
export default {
  components: { Login },
  data () {
    return {
      dialog: false
    }
  },
  mounted () {
  },
  methods: {
    openDialog () {
      this.dialog = true
    },
    closeDialog () {
      this.dialog = false
    },
    menuOpen () {
      $('.nav-container').css('left', 0)
    },
    menuClose () {
      $('.nav-container').css('left', '-100%')
    }
  },
};
</script>
<style>
.logo {
  width: 50px;
  height: 50px;
  display: inline-block;
  margin-left: 20px;
  margin-right: 10px;
  border-radius: 0;
}
.login {
  margin-right: 30px;
  width: 35px;
  height: 35px;
}
li.nav-item.login{
  display: none;
}
.menu-toggler{
  display: none;
}
li.nav-item.closeMenu{
  display: none;
}
div.navbar {
  background-color: lightgray;
  height: 80px;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 1;
  width: 100vw;
  backdrop-filter: blur(20px);
}
li.nav-item {
  display: flex;
  align-items: center;
}
a.nav-link {
  color: #000 !important;
  font-size: 20px;
}
a.nav-link.active {
  text-decoration: underline;
  font-weight: 700;
}
@media (max-width: 680px) {
.nav-container {
  width: 100%;
  height: 100vh;
  background: lightgray;
  position: absolute;
  left: -100%;
  z-index: 1;
  top: 0;
  transition-duration: 1s;
  transition-timing-function: ease-in-out;
  overflow-y: auto !important;
}
  ul.nav{
    display: block;
    text-align: center;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
  }
  li.nav-item{
    justify-content: center;
    font-size: 50px;
  }
  a.nav-link{
    font-size: 35px;
  }
  li.nav-item.login{
    display: contents;
    text-align: center;
  }
  .login{
    display: none;
  }
  .menu-toggler{
    display: block;
    margin-right: 15px;
  }
  li.nav-item.closeMenu {
    display: contents;
  }
}
</style>
