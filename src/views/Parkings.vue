<template>
  <div class="parkings">
      <Navbar />
      <h1>{{this.$store.state.token}}</h1>
  </div>
</template>

<script>
import Navbar from '@/components/Navbar'
export default {
    components:{
        Navbar
    },
    data() {
        return {
            parkings: []
        }
    },
    mounted() {
        this.$store.dispatch("parkings")
        .then((resp)=>{
            this.parkings = resp.data.data
        })
    },
}
</script>

<style>

</style>