<template>
  <header class="inverted">
    <h2>CKEditor 5 Classic in Vue</h2>
  </header>
  <div id="app">
    <ckeditor :editor="editor" v-model="editorData" @ready="onReady" @input="onChange"></ckeditor>
  </div>
  <section class="inverted">
    <p>Edit <code>src/App.vue</code> and save to reload.</p>
    <a href="https://ckeditor.com/docs/ckeditor5/latest/installation/frameworks/vuejs-v3.html">See docs</a>
  </section>
</template>

<script>
import ClassicEditor from '@ckeditor/ckeditor5-build-classic';
import CKEditor from "@ckeditor/ckeditor5-vue"

export default {
  name: 'app',
  components: {
    ckeditor: CKEditor.component
  },
  data() {
    return {
      editor: ClassicEditor,
      editorData: "<p>Hello from CKEditor 5!</p>"
    };
  },
  methods: {
    onReady( editor ) {
      console.log( "CKEditor5 Vue Component is ready to use!", editor );
    },
    onChange( data ) {
      console.log( data );
    }
  }
}
</script>
