<template>
  <div id="add">
    <div class="container">
      <p class="title mb-15">TodoList</p>
      <div class="todo">
        <div class="flex between mb-15">
          <input class="input-add" type="text" v-model.trim="todotext">
          <button class="button add" @click="addToDo">追加</button>
        </div>

        <div class="flex between mb-15" v-for="(todo, index) in lists" :key="index">
          <input class="input-update" type="text" v-model="todo.list">
          <div>
            <button class="button update">更新</button>
            <button @ckick="deleteToDo" class="button delete">削除</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      lists:[
        {list:'パンを買う'},
        {list:'コーヒーを買う'},
      ],
      todotext:""
    };
  },
  methods: {
    addToDo() {
      this.lists.push({
        list: this.todotext
      });
      this.todotext = "";
    },
    deleteToDo() {
      this.lists
    }
    // update() {
    //   this.lists.

    // },
    // destroy() {

    // }
  }
};
</script>


<style scoped>
#add {
  background-color: #2d197c;
  height: 100vh;
  width: 100vw;
  position: relative;
}
.container {
  background-color: #fff;
  width: 50vw;
  padding: 30px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  border-radius: 10px;
}
.title {
  font-weight: bold;
  font-size: 24px;
  color: #000;
}
.input-add {
  width: 80%;
  padding: 5px;
  border-radius: 5px;
  border: 1px solid #ccc;
  font-size: 14px;
}
.input-update {
  width: 30%;
  padding: 5px;
  border-radius: 5px;
  border: 1px solid #ccc;
  font-size: 14px;
}

/*    button    */
.button {
  text-align: left;
  font-size: 12px;
  font-weight: bold;
  padding: 8px 16px;
  border-radius: 5px;
  cursor: pointer;
  transition: 0.4s;
  background-color: #fff;
}
.button:active {
  box-shadow: none; 
  transform: translate3d(0, 3px, 0);
}
.add {
  border: 2px solid #dc70fa;
  color: #dc70fa;
}
.add:hover {
  background-color: #dc70fa;
  border-color: #dc70fa;
  color: #fff;
}
.update {
  border: 2px solid #fa9770;
  color: #fa9770;
  margin-right: 5px;
}
.update:hover {
  background-color: #fa9770;
  border-color: #fa9770;
  color: #fff;
}
.delete {
  border: 2px solid #71fadc;
  color: #71fadc;
}
.delete:hover {
  background-color: #71fadc;
  border-color: #71fadc;
  color: #fff;
}



.mb-15 {
  margin-bottom: 15px;
}
.between {
  justify-content: space-between;
}
.flex {
  display: flex;
}
</style>