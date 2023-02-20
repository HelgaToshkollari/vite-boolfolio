<script>
import axios from 'axios';

export default{
    name:"ProjectsShow",
    data(){
        return{
          project: {},
        }
    },
    
    mounted(){
      axios.get("http://127.0.0.1:8000/api/projects/"+ this.$route.params.id)
        .then((resp)=>{
            this.project = resp.data
        });
    },

}
</script>
<template>
    <div class="container">
        <h1>Project #{{ $route.params.id }}</h1>
        
        
        <div class="row d-flex justify-content-center">
            <div class="col-sm-8 d-flex justify-content-center py-4">
                <div class="card"  style="width: 650px" >
                    <img class="img-fluid" :src="project.cover_img"  alt="" >
                    <div class="card-body">
                        <h5 class="card-title">{{ project.title }}</h5>
                        <p class="card-text">{{ project.description }}</p>
                        <div class="card-title">Technology:
                            <div v-for = " technology in project.technologies" :key="technology.id">
                                <span class="badge rounded-pill text-bg-secondary">{{ technology.name }}</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

        </div>
    

    </div>
</template>