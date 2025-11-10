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
    
    <div class="language-header">
      <div class="lang-col">Dansk</div>
      <div class="lang-col">Engelsk</div>
    </div>
    
    <div v-for="(words, category) in dictionary" :key="category" class="category-section">
      <h2 class="category-title">{{ category }}</h2>
      <div class="words-list">
        <div v-for="(word, index) in words" :key="index" class="word-row">
          <div class="word-cell">{{ word.dansk }}</div>
          <div class="word-cell">{{ word.engelsk }}</div>
        </div>
      </div>
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
