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
          this.title = 'Title Changed!'
      }
  },
  computed: {
    //   changeTitle: function () {
    //       this.title = 'Title Changed!'
    //   }
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
