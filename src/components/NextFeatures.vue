<template>
  <div>
    <div>{{ lg }}</div>
    <code v-for="(issue, index) in issues" :key="index"> {{ issue }} </code>

    <ul>
      <li v-for="(issue, index) in issues" :key="index"> TITLE: {{ issue }}</li>
    </ul>
  </div>
</template>
<script>
import axios from 'axios'


export default {
  name: 'NextFeatures',
  props: [],
  data() {
    return {
      issues : null,
      lg: null
    }
  },
  mounted () {
    axios
      .get('https://api.github.com/repos/vicainelli/gasoline-vs-ethanol-vuejs/issues')
      .then(response => (this.getIssues(response)));
  },
  methods: {
    getIssues: function(response) {
      this.lg = response.length;
      return this.issues = response;
    }
  }
}
</script>