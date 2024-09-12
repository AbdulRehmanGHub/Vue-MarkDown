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
  justify-content: center;
  flex-wrap: wrap;
  gap: 10px;

  width: 100%;
  height: auto;
  min-height: 400px;
}

textarea {
  background-color: honeydew;
  width: 400px;
  height: 200px;
  font-size: 40px;
}

.preview {
  background-color: honeydew;
  width: 400px;
  height: 200px;
  text-align: start;
  font-size: 40px;
}

@media (min-width: 1024px) {
  .markdown-editor {
    width: 100%;
    min-height: 600px;
    flex-direction: column;
    gap: 40px;
    justify-content: center;
    align-items: center;
  }

  textarea {
    width: 80%;
    height: 500px;
    font-size: 50px;
  }

  .preview {
    width: 80%;
    height: 500px;
    font-size: 50px;
  }
}

@media (min-width: 500px) {
  .markdown-editor {
    width: 100%;
    min-height: 500px;
    flex-direction: column;
    gap: 20px;
    justify-content: center;
    align-items: center;
  }

  textarea {
    width: 100%;
    height: 220px;
    font-size: 30px;
  }

  .preview {
    width: 100%;
    height: 220px;
    font-size: 30px;
  }
}
</style>