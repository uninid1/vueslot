<template>
  <div class="my-component">
    <slot name="header"></slot>
    <p v-if="isVisible">{{ content }}</p>
    <button @click="updateContent">Обновить содержимое</button>
    <button @click="toggleVisibility">{{ isVisible ? 'Скрыть содержимое' : 'Показать содержимое' }}</button>
    <slot name="footer"></slot>
  </div>
</template>

<script>
export default {
  name: 'MyComponent',
  data() {
    return {
      content: 'Содержимое по умолчанию.',
      isVisible: true
    }
  },
  methods: {
    updateContent() {
      this.content = 'Обновлено содержимое: ' + new Date().toLocaleTimeString();
      alert('Содержимое обновлено!');
    },
    toggleVisibility() {
      this.isVisible = !this.isVisible;
    }
  }
}
</script>

<style scoped>
.my-component {
  border: 1px solid #ddd;
  padding: 10px;
  background-color: #f9f9f9;
}

button {
  background-color: #007BFF;
  color: white;
  border: none;
  padding: 10px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
  border-radius: 5px;
}

button:hover {
  background-color: #0056b3;
}
</style>