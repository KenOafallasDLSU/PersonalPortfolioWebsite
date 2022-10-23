<script>
  import Navbar from '../components/Navbar.vue'
  import Contact from '../components/Contact.vue'
  import WorkCarousel from '../components/WorkCarousel.vue'

  export default{
    Name: "Main",
    components: {
      Navbar, Contact, WorkCarousel
    }
  }
</script>

<template>
  <div>
    <Navbar />

    <div id="about" class="container flex">
      <div class="split-60 split-left">
        <h1>Kenneth Oafallas</h1>
        <div class="subtitle">Software Engineer</div>
        <p>
          I'm a Philippine-based computer science major with a specialization in software technologies and a minor in Japanese studies. I'm graduating in the first quarter of 2023 from De La Salle University as a Summa Cum Laude candidate. I'm very passionate about technology and learning. Because of that, I have worked on various projects in the fields of low-level languages and architecture, web development, game development, AI and machine learning, mobile development, among others. I love finding ways to make different technologies work together to create novel and valuable experiences.
        </p>
        <p>
          I'm also certified JLPT N5 level, and a native English speaker.
        </p>
      </div>
      <div class="split-40">
        Cant possibly work
      </div>
    </div>

    <WorkCarousel id="work" class="container"/>

    <div id="projects" class="container">
      My Personal Projects
    </div>

    <div id="blog" class="container">
      Check out my blog
    </div>

    <Contact id="contact" />
  </div>
</template>

<style scoped>

</style>