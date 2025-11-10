<template>
  <div class="center">
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
</template>

<script>
import dictionary from './assets/dictionary.json';

export default {
  name: "App",
  data() {
    return {
      words: dictionary
    };
  }
};
</script>
