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
  <div>
    <button 
      @click="toggleAccordion()" 
      class="flex accordion-head" 
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
          stroke-linecap="round"
          stroke-linejoin="round"
        />
      </svg>
    </button>
    
    <div class="accordion-hidden flex" v-show="isOpen">
      <img v-if="project.thumbnail != ''" class="company-logo" :src="project.thumbnail" />
      <div class="flex vertical">
        <p>{{ project.description }}</p>
        <p v-if="project.projectlink != ''">Try it out! {{ project.projectlink}}</p>
        <p v-if="project.repolink != ''">Repository Link {{ project.repolink}}</p>
        <div class="flex">

        </div>
      </div>
      
    </div>
  </div>
</template>

<style scoped>
.accordion-head {
  width: 100%;
}

.accordion-arrow {
  max-height: 20px;
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
</style>