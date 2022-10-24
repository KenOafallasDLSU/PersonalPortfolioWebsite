<script>
  import Navbar from '../components/Navbar.vue'
  import Contact from '../components/Contact.vue'
  import WorkCarousel from '../components/WorkCarousel.vue'
  import Projects from '../components/Projects.vue'

  export default{
    Name: "Main",
    components: {
      Navbar, Contact, WorkCarousel, Projects
    }
  }
</script>

<template>
  <div>

    <div class="flex vertical text-align-center full-center mobile-disclaimer ">
      <p class="mt-1">Mobile site is in development</p>
      <p>It is already usable on mobile</p>
      <p>But best experienced through desktop</p>
      <p>Sorry for the inconvenience</p>
    </div>

    <Navbar />

    <div id="about" class="hero flex split overflow-hidden">
      <div class="hero-left flex vertical justify-center">
        <h1>Kenneth Neil Oafallas</h1>
        <h2 class="mb-1">Software Engineer</h2>
        <p class="mb-1">
          I'm a Philippine-based computer science major with a specialization in software technologies and a minor in Japanese studies. I'm graduating in the first quarter of 2023 from De La Salle University as a Summa Cum Laude candidate. I'm very passionate about technology and learning. Because of that, I have worked on various projects in the fields of low-level languages and architecture, web development, game development, AI and machine learning, mobile development, among others. I love finding ways to make different technologies work together to create novel and valuable experiences.
        </p>
        <p class="mb-2">
          I'm also certified JLPT N5 level, and a native English speaker.
        </p>
        <div>
          <a class="button-primary hero-button" href="mailto:kn.oafallas@gmail.com">
            <div class="button-primary-outline-1"></div>
            <div class="button-primary-outline-2"></div>
            Send Me an Email
          </a>
        </div>
      </div>
      <div class="hero-right mob-justify-center">
        <img class="image-canvas" src="../assets/images/kenneth.webp" alt="Portrait of Kenneth Oafallas">
      </div>
    </div>

    <WorkCarousel id="work" class="scroll-guard mb-3" />

    <Projects id="projects" class="scroll-guard mb-3"/>

    <!-- <div id="blog" class="container  navbar-padding">
      Check out my blog
    </div> -->

    <Contact id="contact" />
  </div>
</template>

<style scoped>
  .mobile-disclaimer {
    width: 80%;
    background: rgb(88, 3, 3);
    margin-top: 2rem;
    margin-left: 2rem;
    color: white;
    display: none;
    border-radius: 12px;
    padding-top: 1rem;
    padding-bottom: 1rem;
    font-weight: bold;
  }

.hero {
  height: 100vh;
  width: 100vw;
}

.hero-left {
  width: 38.5vw;
  margin-right: 4vw;
  margin-left: 12.5vw;
}

.hero-right {
  width: 45vw;
}

.hero-button {
  font-size: 20px;
  padding: 10px 20px;
}

.scroll-guard {
  scroll-margin-top: 10vh;
}

.image-canvas {
  position: relative;
  object-fit: cover;
  object-position: 100% 0%;
  width: 100%;
  height: 100%;
  max-width: 45vw;

  z-index: -200;
}

@media only screen and (min-width: 3000px) {
  
  .hero {
    height: auto;
    min-height: 800px;
    width: 75vw;
    max-width: 1440px;
    margin: auto;
    padding-top: 10vh;
  }

  .hero-left {
    width: 50%;
    margin-right: 4em;
    margin-left: 0vw;
  }

  .hero-right {
    width: 50%;
  }

  .image-canvas {
    position: relative;
    object-fit: cover;
    width: 100%;
    height: 100%;
    max-height: 800px;

    z-index: -200;
  }

}

@media screen and (max-width: 800px) {
  .hero {
    height: auto;
    width: 100vw;
    align-items: center;
  }

  .hero-left {
    width: 90%;
    margin-right: 5px;
    margin-left: 5px;
  }

  .hero-right {
    width: 100%;
    margin-top: 40px;
    margin-left: 10%;
  }

  .hero-button {
    font-size: 20px;
    padding: 10px 20px;
    width: 80%;
  }

  .image-canvas {
    position: relative;
    object-fit: cover;
    object-position: 100% 0%;
    width: 100%;
    height: auto;
    max-width: 80vw;
    max-height: 50vh;

    z-index: -200;

    margin: auto;
  }

  .mobile-disclaimer {
    display: block;
  }
}
</style>