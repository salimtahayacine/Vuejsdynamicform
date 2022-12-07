<template>
  <div class="wrapper">
    <div>
      <input type="text" size="50" placeholder="Name" />
      <input type="text" size="50" placeholder="Email" />
      <div v-for="key in count" :key="key">
        <input
          type="text"
          v-model="values['dynamic-field-' + key]"
          size="50"
          placeholder="Another Field"
          :id="key"
        />
      </div>
    </div>
    <div class="controls">
      <a href="#" id="add_more_fields" @click="add"
        ><i class="fa fa-plus"></i> Add More</a
      >
      <a href="#" id="remove_fields" @click="remove"
        ><i class="fa fa-plus"></i> Remove Field</a
      >
    </div>
    <button class="btn" @click="submit">Get Values</button>
  </div>
</template>

<script>
//import HelloWorldVue from "./components/HelloWorld.vue";
export default {
  name: "App",
  data: function () {
    return {
      count: 1,
      values: {},
    };
  },
  methods: {
    add: function () {
      this.count++;
    },
    remove: function () {
      this.count--;
    },
    submit: function () {
      for (var key of Object.keys(this.values)) {
        console.log(key + " -> " + this.values[key]);
      }
    },
    components: {},
  },
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

body {
  background-color: #f0f5ff;
  color: #fff;
}

.btn {
  width: 50%;
  background: #3f51b5;
  color: white;
  border: 0;
  padding: 7px;
  border-radius: 5px;
}

.wrapper {
  width: 400px;
  margin: 40px auto;
  padding: 10px;
  border-radius: 5px;
  background: white;
  box-shadow: 0px 10px 40px 0px rgba(47, 47, 47, 0.1);
}

input[type="text"] {
  padding: 10px;
  margin: 10px auto;
  display: block;
  border-radius: 5px;
  border: 1px solid lightgrey;
  background: none;
  width: 274px;
  color: black;
}

input[type="text"]:focus {
  outline: none;
}

.controls {
  width: 294px;
  margin: 15px auto;
}

#remove_fields {
  float: right;
}
.controls a i.fa-minus {
  margin-right: 5px;
}

a {
  color: black;
  text-decoration: none;
}

h1 {
  text-align: center;
  font-size: 48px;
  color: #232c3d;
}
</style>
