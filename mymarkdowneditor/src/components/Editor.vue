<template>
  <div id="editor">
    <h1>エディター画面</h1>
    <a id="download" href="#" download="sample.md" @click="download()">ダウンロード</a>
    <div class="editorWrapper">
      <textarea class="markdown" v-model="markdown"></textarea>
      <div class="preview" v-html="preview()"></div>
    </div>
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
.editorWrapper{
  display: flex;
}
.markdown{
  width:50%;
  height:500px;
}
.preview{
  width:50%;
  text-align: left;
}
</style>