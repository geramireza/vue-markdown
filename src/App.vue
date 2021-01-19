<template>
  <Header />
  <div class="container mt-4">
    <Markdown />
  </div>
</template>

<script>
import Markdown from '@/components/Markdown'
import Header from '@/components/Header.vue'
export default {
  components:{
    Header,
    Markdown,
  }
}
</script>

<style>
#app {
  font-family: Arial, Helvetica, sans-serif;
}
</style>
