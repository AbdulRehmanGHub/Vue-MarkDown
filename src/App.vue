<template>
  <div id="heading">
    <h1>< Markdown Editor /></h1>
  </div>
  <div id="app">
    <MarkdownEditor />
  </div>
</template>

<script>
import MarkdownEditor from './components/MarkdownEditor.vue';

export default {
  name: 'App',
  components: {
    MarkdownEditor,
  },
};
</script>

<style>

body{
  display: flex;
  flex-direction: column;
  /* justify-content: center; */
  align-items: center;
  background: #000428;  /* fallback for old browsers */
  background: -webkit-linear-gradient(to right, #004e92, #000428);  /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(to right, #004e92, #000428); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */

}

#heading{
  color: white;
  font-size: 40px;
  font-weight: bold;
  font-family: Georgia, 'Times New Roman', Times, serif;
}

#app {
  display: inline-block;
  font-family: sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 10px 60px;
  /* background-color: aqua; */
}
</style>