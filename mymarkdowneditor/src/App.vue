<template>
  <div id="app">
    <Editor></Editor>
  </div>
</template>

<script>
import Editor from './components/Editor.vue';

export default {
  name: 'app',
  data () {
    return {
      
    }
  },
  components: {
    'Editor': Editor,
  },
}
</script>

<style lang="scss">
@import url("../node_modules/sanitize.css/sanitize.css");
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
}

a {
  color: #42b983;
}
h1{
  margin-top:5px;
  margin-bottom:5px;
}
ul{
  list-style-type: disc;
  padding:5px 20px;
  margin:10px 0;
}
table th{
  border-top:solid 1px black;
}
table th, table td{
  border-bottom:solid 1px black;
  border-left:solid 1px black;
  padding: 2px 5px;
}
table th:last-child,
table td:last-child{
  border-right:solid 1px black;
}

</style>
