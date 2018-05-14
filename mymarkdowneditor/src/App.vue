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
h1,h2,h3,h4,h5,h6{
  margin:5px 0;
}
p{
  margin:10px 0;
}
ul{
  list-style-type: disc;
  padding:5px 20px;
  margin:10px 0;
}
ol{
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
blockquote{
  margin:20px 30px;
  border-left:solid 3px black;
  padding-left: 15px;
}
code{
  background-color: #393939;
  color: #fff;
  padding: 5px 5px;
  text-align: left;
}
hr{
  margin:30px 0;
}

</style>
