<template>
  <div id="editor">
    <h1>My Markdown Editor</h1>
    <div class="editorWrapper">
      <textarea class="markdown" v-model="markdown"></textarea>
      <div class="preview" v-html="preview()"></div>
    </div>
    <a id="download" href="#" download="sample.md" @click="download()">ダウンロード</a>
  </div>
</template>

<script>
import marked from 'marked';
export default {
  name: 'editor',
  data(){
      return{
        markdown:'',
      }
  },
  methods:{
    preview: function(){
      return marked(this.markdown);
    },
    download: function(){
      //var content = this.markdown;
      var blob = new Blob([this.markdown], {"type" : "text/plain"});

      if(window.navigator.msSaveBlob){
        window.navigator.msSaveBlob(blob, "sample.md");
        window.navigator.msSaveOrOpenBlob(blob, "sample.md");
      } else {
        document.getElementById("download").href = window.URL.createObjectURL(blob);
      }
    },
  }
}
</script>

<style lang="scss" scoped>
h1{
  margin-bottom: 10px;
  color: #5AB38B;
}
#download{
  float: left;
  margin-left: 20px;
  text-decoration: none;
}
#download:hover{
  text-decoration: underline;
}
.editorWrapper{
  display: flex;
  margin:20px;
}
.markdown{
  width:50%;
  height:600px;
}
.preview{
  background-color: #E3E3E3;
  width:50%;
  text-align: left;
  margin-left: 30px;
  padding:10px;
}
</style>