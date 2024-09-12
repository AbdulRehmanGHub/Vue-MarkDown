<template>
  <div id="heading">
    <h1>
      < Markdown Editor />
    </h1>
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
body {
  display: flex;
  flex-direction: column;
  align-items: center;
  background: #000428;
  background: -webkit-linear-gradient(to right, #004e92, #000428);
  background: linear-gradient(to right, #004e92, #000428);
}

#heading h1{
  color: white;
  font-size: 28px;
  font-weight: bold;
  font-family: Georgia, 'Times New Roman', Times, serif;
}

#app {
  display: inline-block;
  font-family: sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  width: 90%;
  margin: 10px auto;
  padding: 1rem;
  text-align: center;
}

@media (max-width: 500px) {
  #heading h1{
    font-size: 24px;
  }

  #app {
    max-width: 100%;
    margin: 20px auto;
    padding: 10px 4px;
  }
}

@media (min-width: 768px) and (max-width: 1024px) {
  #heading h1{
    font-size: 40px;
  }

  #app {
    max-width: 100%;
    margin: 20px auto;
    padding: 10px 8px;
  }
}

@media (min-width: 1024px) {
  #heading h1{
    font-size: 60px;
  }

  #app {
    max-width: 100%;
    margin: 14px auto;
  }
}
</style>