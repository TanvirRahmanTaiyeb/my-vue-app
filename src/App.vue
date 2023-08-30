<template>
  <div class="app">
    <!-- Header section -->
    <header class="header">
      <h1 class="title">Vue 3 Concepts</h1>
    </header>

    <!-- Conditional Rendering section -->
    <section class="section">
      <h2 class="section-title">Conditional Rendering:</h2>

      <!-- v-if and v-else example -->
      <div class="example">
        <p v-if="showText" class="condition-text">This is rendered using <strong>v-if</strong></p>
        <p v-else class="condition-text">This is rendered using <strong>v-else</strong></p>
      </div>

      <!-- v-show example -->
      <div class="example">
        <p v-show="showMessage" class="condition-text">This is rendered using <strong>v-show</strong></p>
      </div>

      <!-- v-for example -->
      <div class="example">
        <h3>Items:</h3>
        <ul class="item-list">
          <li v-for="(item, index) in items" :key="index" class="item">{{ item }}</li>
        </ul>
      </div>

      <!-- v-if with v-for example -->
      <div class="example">
        <h3>Items with Visibility:</h3>
        <ul class="item-list">
          <li v-for="item in filteredItems" :key="item.id" class="item">{{ item.name }}</li>
        </ul>
      </div>
    </section>

    <!-- Form Input Handling section -->
    <section class="section">
      <h2 class="section-title">Form Input Handling:</h2>

      <!-- v-model example -->
      <div class="example">
        <input type="text" v-model="inputText" class="input" placeholder="Type something">
        <p class="input-result">You typed: <strong>{{ inputText }}</strong></p>
      </div>

      <!-- Checkbox v-model example -->
      <div class="example">
        <label class="checkbox-label">
          <input type="checkbox" v-model="isChecked" class="checkbox">
          Checkbox is <strong>{{ isChecked ? 'checked' : 'unchecked' }}</strong>
        </label>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // Data for conditional rendering
      showText: true,
      showMessage: true,

      // Data for v-for example
      items: ['Item 1', 'Item 2', 'Item 3'],

      // Data for v-if with v-for example
      itemsWithVisibility: [
        { id: 1, name: 'Item 1', visible: true },
        { id: 2, name: 'Item 2', visible: false },
        { id: 3, name: 'Item 3', visible: true }
      ],

      // Data for v-model example
      inputText: '',
      isChecked: false
    };
  },
  computed: {
    // Computed property for v-if with v-for example
    filteredItems() {
      return this.itemsWithVisibility.filter(item => item.visible);
    }
  }
};
</script>
<style scoped>
.app {
  font-family: Arial, sans-serif;
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
  background-color: #f8f8f8;
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
}

.header {
  text-align: center;
  margin-bottom: 30px;
  padding: 20px 0;
  background-color: #35495e;
  color: #ffffff;
}

.title {
  font-size: 2rem;
  margin: 0;
}

.section {
  margin-bottom: 40px;
}

.section-title {
  font-size: 1.5rem;
  margin-bottom: 20px;
}

.example {
  border: 1px solid #ccc;
  padding: 15px;
  margin-bottom: 20px;
  background-color: #ffffff;
  border-radius: 8px;
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
}

.condition-text {
  margin: 0;
  font-size: 1.1rem;
}

.item-list {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

.item {
  margin-bottom: 5px;
  padding: 5px 0;
  border-bottom: 1px solid #ccc;
}

.input {
  width: 100%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 1rem;
}

.input-result {
  margin-top: 10px;
  font-weight: bold;
}

.checkbox-label {
  display: flex;
  align-items: center;
  font-size: 1rem;
}

.checkbox {
  margin-right: 10px;
}
</style>
