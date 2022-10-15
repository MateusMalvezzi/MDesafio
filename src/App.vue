<template>
  <div id="app">

    <MyHeader />

  </div>
</template>

<script>
import '../src/styles/global.css';

import MyHeader from './components/MyHeader.vue'

export default {
  name: 'App',
  components: {
    MyHeader
  }
}
</script>
