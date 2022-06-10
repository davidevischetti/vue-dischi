<template>
  <div id="app">
    <MyHeader/>
    <MyContent/>
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import MyContent from './components/MyContent.vue'

export default {
  name: 'App',
  components: {
    MyHeader,
    MyContent
}
}
</script>

<style lang="scss">

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
 width: 100%;
 height: 100vh;
}

</style>
