<template>
  <div id="app">
    <my-component>
      <template v-slot:header>
        <h1>Заголовок</h1>
      </template>

      <p>{{ content }}</p>

      <template v-slot:footer>
        <p>Подвал</p>
      </template>
    </my-component>
  </div>
</template>

<script>
import MyComponent from './components/MyComponent.vue'

export default {
  name: 'App',
  components: {
    MyComponent
  },
  data() {
    return {
      content: 'Содержимое по умолчанию.'
    }
  },
  methods: {
    updateContent() {
      this.content = 'Обновлено содержимое: ' + new Date().toLocaleTimeString();
    }
  },
  mounted() {
    setInterval(this.updateContent, 1000);
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color: #e9ecef;
  padding: 20px;
}
</style>