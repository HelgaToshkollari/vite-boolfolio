<script>
import TheHeader from "./components/TheHeader.vue";

export default{
  components:{TheHeader},
  data(){
    return{
      projects: []
    }
  },
  methods: {
    fetchProjects(){
      axios.get("http://127.0.0.1:8000/api/projects").then((resp)=>{
        console.log(resp.data);

      })
    
    } 
  }, 
  mounted(){
    this.fetchProjects();
  }

}
</script>

<template>
  <TheHeader></TheHeader>
 
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
                    <th></th>
                  </tr>
                </thead>
                <tbody>
                <tr v-for="project in projects" :key="project.id">
                  <td>{{ project.cover_img }}</td>
                  <td>{{ project.title }}</td>
                  <td>{{ project.description }}</td>
                  <td>{{ project.technologies }}</td>
                </tr>
                 
                </tbody>
              </table> 
            </div>
            </div>
          </div>
    </div> 
 </div>
</template>

<style lang="scss">
@use "styles/main.scss";

</style>
