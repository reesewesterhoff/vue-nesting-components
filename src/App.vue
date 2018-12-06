<template>
<!-- display components in the order you want them -->
  <div>
    <app-header></app-header>
    <app-ninjas></app-ninjas>
    <app-footer></app-footer>
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

    }
  }
}
</script>

<style>

</style>
