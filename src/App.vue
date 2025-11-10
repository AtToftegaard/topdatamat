<template>
  <div class="center">
    <div class="header">
      <h1>EDB Ordbog</h1>
      <a 
        href="https://github.com/AtToftegaard/topdatamat/edit/main/src/assets/dictionary.json" 
        target="_blank"
        class="contribute-btn"
      >
        Foreslå nye ord
      </a>
    </div>
    
    <div v-for="(words, category) in dictionary" :key="category" class="category-section">
      <h2 class="category-title">{{ category }}</h2>
      <table>
        <thead>
          <tr>
            <th>Dansk</th>
            <th>Engelsk</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(word, index) in words" :key="index">
            <td>{{ word.dansk }}</td>
            <td>{{ word.engelsk }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import dictionary from './assets/dictionary.json';

export default {
  name: "App",
  data() {
    return {
      dictionary: dictionary
    };
  }
};
</script>
