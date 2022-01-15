<template>
  <div class="ToDoList">
    <div id="todo">
      <div class="container">
        <h1>todo</h1>
        <input type="text" v-model="inputData">
        <button class="add" @click="addItemToList">Add</button>
        <ul>
          <li v-for="(item, index) in list" :key="index">{{item}}
            <button class="delet" @click="deletItem(index)">delet</button>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ToDoList',
  data () {
    return {
      list: [],
      inputData: ''
    } 
  },
  methods:{
    addItemToList() {
      this.list.push(this.inputData)
      console.log(this.list)
    },
    deletItem(key) {
      this.list.splice(key,1)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  li {
    list-style-type: none;
  }

</style>
