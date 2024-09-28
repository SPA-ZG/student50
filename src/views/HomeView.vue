<template>
  <div class="home">
    <h3>Project planner</h3>
  <div v-if="projects.length">
    <div v-for="project in projects" :key="project.id">
      <SingleProject :project="project"  @delete="handleDelete" @complete="handleComplete"></SingleProject>
  </div>
  </div>
</div>
</template>

<script>
import SingleProject from "@/components/SingleProject.vue";

export default {
  name: "HomeView",
  components: {SingleProject},
  data(){
    return {
      projects: []
    }
  },
  mounted() {
    fetch("https://fm-lab6-jsonserver.onrender.com/projects", {method: "GET"})
    .then(res => res.json())
    .then(data => this.projects = data)
    .catch(err => console.log(err.message))
  },
  methods:{
    handleDelete(id){
      this.projects = this.projects.filter(item => item.id != id)
    }, 
    handleComplete(id){
      let p = this.projects.find(project => project.id == id)
      p.complete = !p.complete

    }
  }
};
</script>

<style>
 h3 {
  color:blue
 }
</style>

