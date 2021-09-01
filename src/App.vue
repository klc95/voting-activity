<template>
  <div id="app">
    <BasicSettingsPage/>
  </div>
</template>

<script>
import BasicSettingsPage from './components/BasicSettingsPage.vue'
export default {
  name: 'App',
  components: {
    BasicSettingsPage
  }
}
</script>

<style>
    #app{
      background-color: #F3F4F7;
    }
</style>
