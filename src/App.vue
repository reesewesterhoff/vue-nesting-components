<template>
<!-- display components in the order you want them -->
  <div>
    <!-- listens for event to happen, takes in what we passed from child -->
    <app-header v-bind:title="title" v-on:changeTitle="updateTitle($event)"></app-header>
    <app-ninjas v-bind:ninjas="ninjas"></app-ninjas>
    <app-footer v-bind:title="title"></app-footer>
  </div>
</template>

<script>
// import components to show them
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import Ninjas from './components/Ninjas.vue';

export default {
  // tell where to find component and what we want to call it
  components: {
    'app-header': Header,
    'app-ninjas': Ninjas,
    'app-footer': Footer
  },
  data () {
    return {
       ninjas: [
                {name: 'Ryu', speciality: 'Vue Components', show: false},
                {name: 'Crystal', speciality: 'HTML Wizardry', show: false},
                {name: 'Hitoshi', speciality: 'Click Events', show: false},
                {name: 'Tango', speciality: 'Conditionals', show: false},
                {name: 'Kami', speciality: 'Webpack', show: false},
                {name: 'Yoshi', speciality: 'Data Diggin', show: false}
            ],
        title: 'Vue Ninjas'
    }
  },
  methods: {
    // runs function and changes title
    // updated title is passed to child, updates both
    updateTitle: function(updatedTitle) {
      this.title = updatedTitle;
    }
  }
}
</script>

<style>

</style>
