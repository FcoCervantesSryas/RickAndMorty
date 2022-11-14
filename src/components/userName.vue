<template>
  <div>
    <h1>Search for your favorite workmate</h1>
    <input type="text" v-model="input"> <br>
    <ul>
        
      <li v-for="(name, index) in filteredNames" v-bind:key="index">
        {{ name }}
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'userName',
  data() {
    return {
      names: [
        "Parth",
        "Eduard",
        "Frank",
        "Edgar",
        "Max",
        "Chencho",
        "Demian",
        "Alexis",
        "Citlali",
        "Luz",
        "Juan",
        "Juan"
      ],
      input: ""
    }
  },
  computed: {
    filteredNames() {
      if (this.input == "") {
        return []
      }
      return this.names.filter(name => name.toLowerCase().includes(this.input.toLowerCase()))
    }
  }
} 
</script>
<style scoped>
div {
  display: flex;
  flex-direction: column;
  align-items: center;
}

h1 {
  height: 100px;
  width: 100%;
  color: white;
  font-size: 70px;
  background-color: rgb(0, 0, 94);
}

input {
  width: 100px;
  margin: 0xp;
}

ul {
  width: 100px;
  list-style-type: none;
  display: flex;
  flex-flow: column;
  margin: 0;
  padding: center;
}

li {
  background-color: gray;
  width: 100%;
  text-justify: center;
  color: black;

}

li:hover {
  background-color: black;
  color: white;
}
</style>