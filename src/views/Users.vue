<template>
  <div class="users">
      <Navbar />
      <h1> {{ show }} </h1>
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
      show:[]
    }
  },
  mounted() {
    this.$store.dispatch("users")
    .then((resp)=>{
      this.show = resp.data.data
      console.log(this.show);
    })
  },
}
</script>

<style>

</style>