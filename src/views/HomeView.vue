<script>
// @ is an alias to /src
import NavBar from '@/components/Home/NavBar.vue'
import Header from '@/components/Header.vue'
import HomeMain from '@/components/Home/HomeMain.vue'
import HomeFooter from '@/components/Home/HomeFooter.vue'
export default {
  name: 'HomeView',
  components: {
    NavBar,Header,HomeFooter,HomeMain
  }
}
</script>
<template>
  <div>
    <Header/>
    <div>
      <HomeMain/>
    </div>
    <HomeFooter/>
  </div>
</template>
<style>
</style>
