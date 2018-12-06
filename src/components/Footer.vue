<template>
  <footer>
      <p>{{copyright}} {{title}}</p>
  </footer>
</template>

<script>
import {bus} from '../main';

export default {
    props: {
        title: {
            type: String
        }
    },
  data () {
    return {
        copyright: 'Copyright 2018' 
    }
  },
  // life cycle hook, starts listening when component is created
  created () {
      // listens for function that we passed from Header to fire
      // gathers data that we passed
      bus.$on('titleChanged', (data) => {
          // changes title in footer to the data that we passed
          this.title = data;
      })
  }
}
</script>

<style scoped>
footer {
    background-color: #222;
    padding: 6px;
}

p {
    color: lightgreen;
    text-align: center;
}
</style>
