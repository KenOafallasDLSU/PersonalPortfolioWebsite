<script>
  export default{
    Name: "Navbar"
  }

  /* When the user scrolls down, hide the navbar. When the user scrolls up, show the navbar */
  let prevScrollpos = window.pageYOffset;
  window.onscroll = function() {
    let currentScrollPos = window.pageYOffset;
    if (prevScrollpos > currentScrollPos) {
      document.getElementById("navbar").style.top = "0";
    } else {
      document.getElementById("navbar").style.top = "-10vh";
    }
    prevScrollpos = currentScrollPos;
  }
</script>

<template>
  <div id="navbar" class="navbar">
    <div class="navbar-left">
      <a href="#about">About</a>
      <a href="#work">Work</a>
      <a href="#projects">Projects</a>
      <a href="#contact">Contact</a>
      <!-- <a href="#blog">Blog</a> <br> -->
    </div>
    
    <div class="navbar-right">
      <a href="mailto:kn.oafallas@gmail.com" target="_blank" rel="noopener">Email</a>
      <a href="https://www.linkedin.com/in/kenneth-oafallas/" target="_blank" rel="noopener">LinkedIn</a>
      <a href="https://github.com/KenOafallasDLSU" target="_blank" rel="noopener">Github</a>
    </div>
  </div>
</template>

<style scoped>
.navbar {
  position: fixed;
  width: 75vw;
  height: 10vh;
  padding-left: 12.5vw;
  padding-right: 12.5vw;

  font-size: 20px;

  background-color: rgb(251, 251, 251);
  border-bottom: 1px solid rgb(52, 52, 52);

  display: flex;
  justify-content: space-between;

  transition: top 0.3s;

  z-index: 99999;
}

.navbar-left {
  height: 100%;
  width: 50%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.navbar-right {
  height: 100%;
  width: 25%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

a {
  text-decoration: none;
  color: rgb(255, 142, 236);
  transition: 0.4s;
  font-weight: bold;
  -webkit-text-stroke-width: 0.5px;
  -webkit-text-stroke-color: rgb(69, 69, 69);
}

a:hover {
  color: black;
  -webkit-text-fill-color: rgb(255, 142, 236); /* Will override color (regardless of order) */
  -webkit-text-stroke-width: 1.5px;
  -webkit-text-stroke-color: black;
}
</style>