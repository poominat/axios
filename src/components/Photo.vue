<template>
    <div>

<ul>
    <li v-for="photo in photolist" :key = "photo.id">
        id {{photo.id}} : {{photo.title}}
        <img src="photo.thumbnailUrl">
    </li>
</ul>
    </div>

</template>

<script>
import axios from"axios"; 

export default {
    data(){
        return{
            photolist:null,
            errored:false,
            loading:false,
        }
    },

    mounted(){
        axios
      .get('http://jsonplaceholder.typicode.com/photos')
      .then(response => {
        this.photolist = response.data.slice(1,20)
      })
      .catch(error => {
        console.log(error)
        this.errored = true
      })
      .finally(() => this.loading = false)
    }
}
</script>


<style>

</style>














