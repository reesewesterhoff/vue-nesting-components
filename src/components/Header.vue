<template>
  <div>
      <header>
          <!-- when passing a primitive prop, changes only occur in the component -->
          <!-- where they were made -->
          <h1 v-on:click="changeTitle">{{title}}</h1>
      </header>
  </div>
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

    }
  },
  methods: {
      // works but throws error in the console saying not to do it 
      // because it will be overwritten when parent component re renders
      changeTitle: function () {
          // fires event up to parent, pass name and what you want it to change to
        //   this.$emit('changeTitle', 'Title Changed');

        // changes title locally
        this.title = 'Vue Wizards';
        // emits a change on the bus, give it function name and data
        bus.$emit('titleChanged', 'Vue Wizards');
      }
  }
}
</script>

<style scoped>
header {
    background-color: lightgreen;
    padding: 10px;
}

h1 {
    color: #222;
    text-align: center;
}

</style>
