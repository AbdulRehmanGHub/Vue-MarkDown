<template>
    <div class="markdown-editor">
      <textarea v-model="markdown" @input="updatePreview"></textarea>
      <div class="preview" v-html="html"></div>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent, ref } from 'vue';
  import { marked } from 'marked';
  
  export default defineComponent({
    setup() {
      const markdown = ref('');
      const html = ref('');
  
      const updatePreview = () => {
        const result = marked(markdown.value);
        if (result instanceof Promise) {
          result.then(res => {
            html.value = res;
          });
        } else {
          html.value = result;
        }
      };
  
      return {
        markdown,
        html,
        updatePreview,
      };
    },
  });
  </script>
  
  <style scoped>
  .markdown-editor {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 20px;
  }
  
  textarea {
    background-color: honeydew;
    width: 400px;
    height: 200px;
    margin-bottom: 20px;
  }
  
  .preview {
    background-color: honeydew;
    width: 400px;
    height: 200px;
    margin-bottom: 20px;
    text-align: start;
  }
  </style>
  