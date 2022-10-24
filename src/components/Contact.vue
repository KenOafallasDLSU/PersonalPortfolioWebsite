<script>
import { createConditionalExpression } from '@vue/compiler-core'

  export default{
    Name: "Contact",
    data: function() {
      return {
        trail: []
      }
    },
    methods: {
      drawtrail: function(event) {
        //console.log(this.trail)

        let el = this.$refs.contactsection
        let top = el.getBoundingClientRect().top // - el.ownerDocument.defaultView.pageYOffset

        this.trail.push({ x: event.clientX, y: event.clientY - top})
        if(this.trail.length > 40) this.trail.shift();
      },
      randomangle: function() {
        let random = Math.floor(Math.random() * 360)
        //console.log(random)
        return random
      }
    }
  }
</script>

<template>
  <div ref="contactsection" class="full-height flex vertical full-center contact-container" @mousemove="drawtrail">

    <template v-for="point in trail">
      <div class="cursor-trail" :style="{left: point.x + 'px', top: point.y + 'px', rotate: randomangle()+'deg'}">
        <!-- {{point.x}} {{point.y}} -->
      </div>
    </template>

    <h2 class="mb-2 text-align-center">Open for Work!</h2>
    <p class="text-align-center">I'm always up for an opportunity to learn new technologies and work on interesting projects.</p>
    <p class="mb-3 text-align-center">If you think I'm a good fit for your project, please don't hesitate to contact me.</p>
    
    <div class="mb-3">
      <a class="button-secondary email-btn" href="mailto:kn.oafallas@gmail.com">
        Send Me an Email
      </a>
    </div>
    <div class="">
      <a class="button-primary linkedin-btn" href="https://www.linkedin.com/in/kenneth-oafallas/" target="_blank" rel="noopener">
        <div class="button-primary-outline-1"></div>
        <div class="button-primary-outline-2"></div>
        Connect on LinkedIn
      </a>
    </div>
  </div>
</template>

<style scoped>
h2 {
  font-size: 50px;
}

p {
  font-size: 20px;
}

.email-btn {
  font-size: 20px;
  padding: 10px 20px;
  margin-bottom: 3rem;
}

.linkedin-btn {
  font-size: 20px;
  padding: 10px 20px;
}

.contact-container {
  position: relative;
}

.cursor-trail {
    position: absolute;

    z-index: 10000;
    width: 4px;
    height: 4px;
    margin: 0;
    padding: 0;
    border: 2px solid white;
    outline: 2px solid black;
    border-radius: 0%;

    background: black;
    pointer-events: none;

    color: white;
}
</style>