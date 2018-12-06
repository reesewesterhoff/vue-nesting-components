<template>
    <div id="ninjas">
        <ul>
            <!-- cycle through ninjas array -->
            <li v-for="ninja in ninjas" 
                :key=ninja.name 
                v-on:click="ninja.show = !ninja.show">
                <h2>{{ninja.name}}</h2>
                <!-- shows or doesn't show speciality depending on show property -->
                <h3 v-show="ninja.show">{{ninja.speciality}}</h3>
            </li>
        </ul>
        <button v-on:click="deleteNinja">Delete Ninja</button>
    </div>
</template>

<script>
export default {
    // recieves props as though it were written in data section
    // props: ['ninjas']
    
    // can perform validation by making props an object
    // and specifying what it should expect
    // will throw an error if it does not get what it's expecting
    props: {
        ninjas: {
            type: Array,
            // will fail if ninjas is not passed down
            required: true
        }
    },
    data () {
        return {
       
    }
  },
  methods: {
      // able to access props through methods as well with this.PROPS
    //   test: function () {
    //       this.ninjas
    //   }

    // with a reference data type, changes occur in all components using 
    // that reference
    deleteNinja: function() {
        this.ninjas.pop();
    }
  }
}
</script>

<style scoped>
#ninjas{
    width: 100%;
    max-width: 1200px;
    margin: 40px auto;
    padding: 0 20px;
    box-sizing: border-box;
}
ul{
    display: flex;
    flex-wrap: wrap;
    list-style-type: none;
    padding: 0;
}
li{
    flex-grow: 1;
    flex-basis: 300px;
    text-align: center;
    padding: 30px;
    border: 1px solid #222;
    margin: 10px;
}
</style>
