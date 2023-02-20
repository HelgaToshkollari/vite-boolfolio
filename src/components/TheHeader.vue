<template>
    <div>
        <nav class="navbar navbar-expand-lg navbar-light bg-light px-4">
        

            <div class="collapse navbar-collapse justify-content-between" id="navbarSupportedContent">
                <ul class="navbar-nav d-flex">
                    <li class="nav-item active" v-for="(link, index) in menuLinks" :key="index">

                      <!--<a class="nav-link" :href="link.link"></a>-->
                      <router-link :to="{name: link.routeName}" class="nav-link" >{{ link.label }}</router-link>
                    </li>

                    
                </ul>
                <form class="form-inline my-2 my-lg-0 d-flex">
                  <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search">
                  <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
                </form>
            </div>
        </nav>
    </div>
</template>
<script>
export default{
  
    data(){  
        return{
            menuLinks: [
            {
                label:"Home",
                routeName:"home"
            },
            {
                label:"Projects",
                routeName:"projects.index"
            },
            {
                label:"About us",
                routeName:"about"
            },
            {
                label:"Contacts",
                routeName:"contacts"
            },
            ]
        }

    }
}

</script>

<style scoped lang="scss">

</style>