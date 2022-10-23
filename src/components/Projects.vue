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
  <div class="container">
    <h2>Personal and Academic Projects</h2> 

    <div class="flex">
      <div id="web-filter" @click="filterCriteria = 'web'">
        Web Dev
      </div>
      <div id="low-level-filter" @click="filterCriteria = 'low'">
        Low-Level and Arch
      </div>
      <div id="games-filter" @click="filterCriteria = 'games'">
        Games
      </div>
      <div id="ai-filter" @click="filterCriteria = 'ai'">
        AI and ML
      </div>
      <div id="mobile-filter" @click="filterCriteria = 'mobile'">
        Mobile Dev
      </div>
    </div>
    
    <ProjectItem v-for="project in renderedProjects" :key="project.title" :project="project" />
  </div>
</template>

<style scoped>

</style>