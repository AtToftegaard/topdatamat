<template>
  <div class="center">
    <header class="header">
      <h1>EDB Ordbog</h1>
      <a 
        href="https://github.com/AtToftegaard/edb-ordbog/edit/main/src/assets/dictionary.json" 
        target="_blank"
        rel="noopener noreferrer"
        class="contribute-btn"
        aria-label="Foreslå nye ord til ordbogen"
      >
        Foreslå nye ord
      </a>
    </header>
    
    <main>
      <div class="language-header" role="row">
        <div class="lang-col" role="columnheader">Dansk</div>
        <div class="lang-col" role="columnheader">Engelsk</div>
      </div>
      
      <section v-for="(words, category) in dictionary" :key="category" class="category-section">
        <h2 class="category-title">{{ category }}</h2>
        <div class="words-list" role="table" :aria-label="`${category} termer`">
          <div v-for="(word, index) in words" :key="index" class="word-row" role="row">
            <div class="word-cell" role="cell">{{ word.dansk }}</div>
            <div class="word-cell" role="cell">{{ word.engelsk }}</div>
          </div>
        </div>
      </section>
    </main>
    
    <footer class="footer">
      <p>© 2025 EDB Ordbog | <a href="https://github.com/AtToftegaard/edb-ordbog" target="_blank" rel="noopener noreferrer">GitHub</a></p>
    </footer>
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
