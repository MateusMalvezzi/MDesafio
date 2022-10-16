<template>
  <div id="app">

    <MyProject />

  </div>
</template>

<script>
import '../src/styles/global.css';

import MyProject from './components/MyProject.vue'

export default {
  name: 'App',
  components: {
    MyProject
  }
}
</script>
