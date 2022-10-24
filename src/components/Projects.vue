<script>
  import projectsJSON from '../data/projects.json'
  import ProjectItem from '../components/ProjectItem.vue'
  export default{
    Name: "Projects",
    components: {
      ProjectItem
    },
    data: function() {
      return {
        projects: projectsJSON,
        filterCriteria: "low"
      }
    },
    computed: {
      renderedProjects: function() {
        return this.projects.filter((project) => {
          return project.tags.includes(this.filterCriteria)
        })
      }
    }
  }
</script>

<template>
  <div class="project-container">
    <div class="project-canvas"></div>
    <div class="container flex vertical align-center">
      <h2 class="mb-2">Personal and Academic Projects</h2> 

      <div class="filter-group mb-3">
        <div class="flex vertical align-center pointer filter-button" id="web-filter" @click="filterCriteria = 'web'">
          <img class="filter-logo" :class="{'filter-selected': filterCriteria == 'web'}" src="../assets/images/web-logo.png" alt="Select Web Dev Projects">
          <div class="filter-label">Web<br>Dev</div>
        </div>
        <div class="flex vertical align-center pointer filter-button" id="low-level-filter" @click="filterCriteria = 'low'">
          <img class="filter-logo" :class="{'filter-selected': filterCriteria == 'low'}" src="../assets/images/archi-logo.png" alt="Select Low-Level Language Projects">
          <div class="filter-label">Low-Level<br>and Arch</div>
        </div>
        <div class="flex vertical align-center pointer filter-button" id="games-filter" @click="filterCriteria = 'games'">
          <img class="filter-logo" :class="{'filter-selected': filterCriteria == 'games'}" src="../assets/images/games-logo.png" alt="Select Game Dev Projects">
          <div class="filter-label">Game<br>Dev</div>
        </div>
        <div class="flex vertical align-center pointer filter-button" id="ai-filter" @click="filterCriteria = 'ai'">
          <img class="filter-logo" :class="{'filter-selected': filterCriteria == 'ai'}" src="../assets/images/ai-logo.png" alt="Select AI and ML Projects">
          <div class="filter-label">AI and<br>ML</div>
        </div>
        <div class="flex vertical align-center pointer filter-button" id="mobile-filter" @click="filterCriteria = 'mobile'">
          <img class="filter-logo" :class="{'filter-selected': filterCriteria == 'mobile'}" src="../assets/images/mobile-logo.png" alt="Select Mobile Dev Projects">
          <div class="filter-label">Mobile<br>Dev</div>
        </div>
      </div>
      
      <ProjectItem v-for="project in renderedProjects" :key="project.title" :project="project" />
    </div>
  </div>
</template>

<style scoped>
.filter-group {
  width: 100%;
  display: flex;
  justify-content: space-around;
  text-align: center;
}

.filter-logo {
  width: 100%;
  max-width: 100px;
  object-fit: contain;
  filter: brightness(0) saturate(100%);
  opacity: 0.25;
}

.filter-button:hover .filter-logo, .filter-button.hover .filter-logo { 
  opacity: 0.6;
}

.filter-selected {
  opacity: 1;
}

.filter-label {
  font-family: 'Raleway', sans-serif;
  font-weight: 600;
}

.project-container {
  border: 3px solid black;
  width: 85vw;
  margin: auto;
  padding-top: 1rem;
  padding-bottom: 3rem;
  min-height: 70vh;

  position: relative;

  max-width: 1440px;
}

.project-canvas {
  position: absolute;
  border: 3px solid black;
  width: 100%;
  height: 100%;
  top: -10px;
  left: 4px;

  z-index: -100;

  max-width: 1440px;
}

@media only screen and (min-width: 3000px) {
  .project-container {
    min-height: 0;
  }

  .filter-label {
    font-size: 8px;
  }
}
</style>