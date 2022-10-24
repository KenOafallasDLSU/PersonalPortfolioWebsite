<script>
  export default{
    Name: "ProjectItem",
    props: ['project'],
    data() {
    return {
      isOpen: false,
    };
    },
    methods: {
      toggleAccordion() {
        this.isOpen = !this.isOpen;
      },
    },
  }
</script>

<template>
  <div class="flex vertical no-shrink project-item">
    <button 
      @click="toggleAccordion()" 
      class="flex accordion-head pointer" 
      :aria-expanded="isOpen"
    >
  
      {{ project.title }}
      
      <svg
        class="accordion-arrow"
        :class="{
          'rotate-180': isOpen,
          'rotate-0': !isOpen,
        }"
        fill="none"
        stroke="currentColor"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 16 10"
        aria-hidden="true"
      >
        <path
          d="M15 1.2l-7 7-7-7"
          stroke-width="2"
          stroke-linecap="square"
          stroke-linejoin="miter"
        />
      </svg>
    </button>
    
    <div class="accordion-hidden flex split" v-show="isOpen">
      <img v-if="project.thumbnail != ''" class="project-img mr-2" :src="project.thumbnail" />
      <div class="flex vertical">
        <p class="mb-2">{{ project.description }}</p>
        
        <div class="flex split mb-1">
          <a class="button-primary project-btn mr-2" v-if="project.projectlink != ''"
           :href="project.projectlink" target="_blank" rel="noopener"
          >
            <div class="button-primary-outline-1"></div>
            <div class="button-primary-outline-2"></div>
            TRY IT OUT!
          </a>
          <a class="button-secondary repo-btn" v-if="project.repolink != ''"
           :href="project.repolink" target="_blank" rel="noopener"
          >
            REPO LINK
          </a>
        </div>
        <div class="flex" id="tech-stack-section">
          <div class="inline tech-label">Tech Stack: </div>
          <template v-for="tech in project.tech">
            <div class="tech-tag">{{ tech }}</div>
          </template>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.accordion-head {
  width: 100%;
  justify-content: space-between;
  padding-top: 10px;
  padding-bottom: 10px;
  padding-left: 20px;
  padding-right: 20px;
  margin-bottom: 10px;
  text-align: left;

  font-family: 'Montserrat', sans-serif;
  font-weight: 600;
  font-size: 16px;

  background-color: rgba(0, 0, 0, 0.1);
  color: black;
  border: none;
}

.no-shrink {
  width: 100%;
  flex-shrink: 0;
}

.accordion-arrow {
  min-height: 15px;
  max-height: 15px;
}

.accordion-hidden {
  border-bottom: 2px solid black;
  border-left: 2px solid black;
  border-right: 2px solid black;
  padding: 3rem;
  margin-bottom: 10px;
}

.company-logo {
  max-height: 70px;
  object-fit: contain;
  margin-right: 15px;
}

.rotate-180 {
  transition: 0.3s;
  transform: rotate(180deg);
}

.rotate-0 {
  transition: 0.3s;
  transform: rotate(0deg);
}

.tech-label {
  font-family: 'Montserrat', sans-serif;
  margin-right: 1rem;
}

.tech-tag {
  display: inline;
  background-color: rgba(0, 0, 0, 0.1);
  border-radius: 5px;

  font-size: 12px;
  font-weight: bold;

  margin-right: 1rem;
  padding: 2px 8px;

  font-family: 'Montserrat', sans-serif;
}

.project-img {
  max-width: 150px;
  max-height: 150px;
  object-fit: cover;
}

.project-item {
  max-width: 95%;
}

@media screen and (max-width: 800px) {
  #tech-stack-section {
    display: none;
  }

  .accordion-hidden {
    padding: 1rem;
  }
}
</style>