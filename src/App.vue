<script>
import TheHeader from "./components/TheHeader.vue";
import axios from "axios";

export default{
  components:{TheHeader},
  data(){
    return{
      projects: []
    }
  },
  methods: {
    fetchProjects(){
      axios.get("http://127.0.0.1:8000/api/projects")
      .then((resp)=>{
        this.projects = resp.data;

      })
    
    } 
  }, 
  mounted(){
    this.fetchProjects();
  },

};
</script>

<template>
  <TheHeader></TheHeader>

  <router-view></router-view>
 
 <!--
  <div class="container">
    <div class="row justify-content-center py-4">
          <div class="col-md-9">
            <div class="card">
            <div class="card-body">
              <table class="table">
                <thead>
                  <tr>
                    <th>Cover</th>
                    <th>Title</th>
                    <th>Description</th>
                    <th>technologies</th>
                  </tr>
                </thead>
                <tbody>
                <tr v-for="project in projects" :key="project.id">
                  <td> <img :src="project.cover_img "  alt="" style="width: 90px">
                   </td>
                  <td><a :href="projects"></a>{{ project.title }}</td>
                  <td>{{ project.description }}</td>
                  <td> 
                    <div v-for="technology in project.technologies" :key="technology.id">
                      {{ technology.name }}

                    </div>
                   </td>
                </tr>
                 
                </tbody>
              </table> 
            </div>
            </div>
          </div>
    </div> 
 </div>
 -->
</template>

<style lang="scss">
@use "styles/main.scss";

</style>
