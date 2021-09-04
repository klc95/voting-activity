<template>
  <div id="app">
    <!-- <BasicSettings/> -->
    <PageSettings/>
    <Test/>
  </div>
</template>

<script>
// import BasicSettings from './components/BasicSettings/BasicSettings.vue'
import PageSettings from './components/PageSettings/PageSettings.vue'

export default {
  name: 'App',
  components: {
    // BasicSettings
    PageSettings
  }
}
</script>

<style>
    
</style>
