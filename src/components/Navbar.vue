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
  <div id="navbar" class="navbar-bg">
    <div class="navbar-content">
      <div class="navbar-left">
        <a class="mr-2" href="#about">About</a>
        <a class="mr-2" href="#work">Work</a>
        <a class="mr-2" href="#projects">Projects</a>
        <a class="mr-2" href="#contact">Contact</a>
        <!-- <a href="#blog">Blog</a> <br> -->
      </div>
      
      <div class="navbar-right">
        <a class="ml-2" href="mailto:kn.oafallas@gmail.com" target="_blank" rel="noopener">Email</a>
        <a class="ml-2" href="https://www.linkedin.com/in/kenneth-oafallas/" target="_blank" rel="noopener">LinkedIn</a>
        <a class="ml-2" href="https://github.com/KenOafallasDLSU" target="_blank" rel="noopener">Github</a>
      </div>
    </div>
  </div>
</template>

<style scoped>
.navbar-bg {
  position: fixed;
  width: 100vw;
  height: 10vh;
  
  background-color: black;
  border-bottom: 5px solid rgb(82, 82, 82);

  transition: top 0.3s;

  z-index: 99999;

  display: flex;
  flex-direction: row;
  justify-content: center;
}

.navbar-content {
  display: flex;
  justify-content: space-between;
  align-items: center;

  padding-left: 12.5vw;
  padding-right: 12.5vw;
  max-width: 1440px;

  width: 100%;
  margin: auto;

  font-size: 20px;
}

.navbar-left {
  height: 100%;
  width: 50%;
  display: flex;
  justify-content: left;
  align-items: center;

  max-width: 600px;
}

.navbar-right {
  height: 100%;
  width: 25%;
  display: flex;
  justify-content: right;
  align-items: center;
}

a {
  text-decoration: none;
  color: white;
  font-weight: bold;

  font-family: 'Raleway', sans-serif;
}

a:hover {
  color: white;
  -webkit-text-fill-color: black; /* Will override color (regardless of order) */
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: white;
}

@media screen and (max-width: 800px) {
  #navbar {
    display: none;
  }
}
</style>