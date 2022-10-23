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
    <Navbar />

    <div id="about" class="container full-height flex">
      <div class="split-60 split-left flex vertical justify-center">
        <h1>Kenneth Oafallas</h1>
        <div class="subtitle">Software Engineer</div>
        <p>
          I'm a Philippine-based computer science major with a specialization in software technologies and a minor in Japanese studies. I'm graduating in the first quarter of 2023 from De La Salle University as a Summa Cum Laude candidate. I'm very passionate about technology and learning. Because of that, I have worked on various projects in the fields of low-level languages and architecture, web development, game development, AI and machine learning, mobile development, among others. I love finding ways to make different technologies work together to create novel and valuable experiences.
        </p>
        <p>
          I'm also certified JLPT N5 level, and a native English speaker.
        </p>
      </div>
      <div class="split-40 flex vertical justify-center">
        Cant possibly work
      </div>
    </div>

    <WorkCarousel id="work" />

    <Projects id="projects" />

    <!-- <div id="blog" class="container  navbar-padding">
      Check out my blog
    </div> -->

    <Contact id="contact" />
  </div>
</template>

<style scoped>

</style>