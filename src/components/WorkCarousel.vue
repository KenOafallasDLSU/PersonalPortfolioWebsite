<script>
  export default{
    Name: "WorkCarousel",
    data: function() {
      return {
        slides: {},
        curSlide: 0,
        maxSlide: 0
      }
    },
    mounted() {
      this.slides = document.querySelectorAll(".slide")
      this.maxSlide = this.slides.length-1

      // loop through slides and set each slides translateX
      this.slides.forEach((slide, indx) => {
        slide.style.transform = `translateX(${indx * 100}%)`
      });
    },
    methods: {
      nextSlide: function() {
        // check if current slide is the last and reset current slide
        if (this.curSlide === this.maxSlide) {
          this.curSlide = 0
        } else {
          this.curSlide++
        }

        //   move slide by -100%
        this.slides.forEach((slide, indx) => {
          slide.style.transform = `translateX(${100 * (indx - this.curSlide)}%)`
        });
      },

      prevSlide: function() {
        // check if current slide is the first and reset current slide to last
        if (this.curSlide === 0) {
          this.curSlide = this.maxSlide
        } else {
          this.curSlide--
        }

        //   move slide by 100%
        this.slides.forEach((slide, indx) => {
          slide.style.transform = `translateX(${100 * (indx - this.curSlide)}%)`
        });
      }
    }
  }
</script>

<template>
  <div class="container flex vertical full-center">

    <h2>My Work Experience</h2>
    
    <div class="slider">
      <div class="slide flex vertical full-center">
        <div class="flex m-bot-1">
          <img class="company-logo" src="../assets/images/megacat-logo.png" alt="Mega Cat Studios Logo">
          <div class="flex vertical">
            <div>Mega Cat Studios</div>
            <div>Junior Game Developer</div>
            <div>July 2022 - October 2022</div>
          </div>
        </div>
        
        <p class="slide-text">
          I worked at Mega Cat, a Pennsylvania, USA-based game studio, for my undergraduate internship focusing on the technical aspects of game development. During my internship, I was exposed to different teams working on a mid-tier game, which provided me with the invaluable experience of being part of a project with significantly larger scope than a start-up or academic project. I went through Quality Assurance to learn bug testing and documentation, Technical Art to learn how to make and use shaders, and Test Engineering to automate testing and data collection.
        </p>
      </div>

      <div class="slide flex vertical full-center">
        <div class="flex m-bot-1">
          <img class="company-logo" src="../assets/images/blue-entity-logo.png" alt="Blue Entity Logo">
          <div class="flex vertical">
            <div>Blue Entity Technologies</div>
            <div>Web Developer</div>
            <div>September 2021 - January 2022</div>
          </div>
        </div>
        
        <p class="slide-text">
          I worked at Blue Entity technologies when they were an early-stage startup, with my main responsibilities being front-end development and maintaining the Content Management System.
          I translated wireframes and Adobe XD concepts into functional and responsive websites, with consideration for Search Engine Optimization and integration with a CMS. I mainly developed marketing websites for international clients, using techniques like animations and horizontal scrolling for a better and more memorable user experience for their customers
          Here is a sample project I worked on as the lead developer https://www.thepathway.com/ , and a larger project where I was a team member https://www.englishoms.com/
        </p>
      </div>

      <!-- Control buttons -->
      <button class="btn btn-next" @click="nextSlide()"> > </button>
      <button class="btn btn-prev" @click="prevSlide()"> &lt; </button>
    </div>

    <div>
      {{curSlide + 1}} of {{slides.length}}
    </div>
  </div>
</template>

<style scoped>
.slider {
  width: 100%;
  max-width: 1000px;
  height: 450px;
  position: relative;
  overflow: hidden; /* <===  */
  border-radius: 15px;
  
  border: 2px solid rgb(255, 142, 236);
}

.slide {
  width: 100%;
  max-width: 1000px;
  height: 450px;
  position: absolute;
  transition: all 0.5s;
  background: white;
}

.slide-text {
  width: 70%;
}

.btn {
  position: absolute;
  width: 40px;
  height: 40px;
  padding: 10px;
  border: none;
  border-radius: 50%;
  z-index: 10px;
  cursor: pointer;
  background-color: rgb(35, 35, 35);
  font-size: 18px;
  color: white;
}
.btn:active {
  transform: scale(1.1);
}
.btn-prev {
  top: 45%;
  left: 2%;
}

.btn-next {
  top: 45%;
  right: 2%;
}

.company-logo {
  max-height: 70px;
  object-fit: contain;
  margin-right: 15px;
}
</style>