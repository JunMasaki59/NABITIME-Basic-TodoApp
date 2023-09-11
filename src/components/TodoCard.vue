<script setup>
import { reactive } from "vue";
const toDoList = reactive([
  {
    title: "プログラミングテスト",
    isDone: false,
  },
  {
    title: "ランニング",
    isDone: true,
  },
]);

let newListTitle ="";

const addList = ( item ) => {
  toDoList.push({ title: item, isDone: false });
  newListTitle = "";
}

const changeIsDone = (item) => {
  item.isDone = !item.isDone;
  console.log(item.isDone);
}
</script>

<template>
  <div class="parent">
    <div class="allWrapper">
      <h1 class="title">ToDo</h1>
      <ul class="toDoListWrapper">
        <li v-for="(item, index) in toDoList" :key="index" class="didNotThing" :class="{ 'didThing' : item.isDone}">
          <label class="task" >
            {{ item.title }}
            <input v-if="item.isDone" type="checkbox" name="toDo" class="checkbox" checked @click="changeIsDone(item)"/>
            <input v-if="!item.isDone" type="checkbox" name="toDo" class="checkbox" @click="changeIsDone(item)"/>
          </label>
        </li>
      </ul>
      <form class="Form">
        <input type="text" name="addToDo" class="Form-Text" v-model="newListTitle" onkeypress="if(event.keyCode===13){event.returnValue=false} "/>
        <input type="button" value="追加" name="AddButton" class="AddButton" @click="addList(newListTitle)" />
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "ToDoCard" /*,
  props: {
    msg: String
  }*/,
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  box-sizing: border-box;
}
.parent {
  display: flex;
  flex-direction: row;
  margin: 0;
  padding: 70px;
  height: 100%;
  width: 100%;
  justify-content: center;
}
.allWrapper {
  display: flex;
  flex-direction: column;
  gap: 20px;
  width: 100%;
  max-width: 1000px;
  height: 100%;
  margin: 0;
  align-self: center;
}

.title {
  margin: 0;
  text-align: center;
  font-size: 40px;
}

.toDoListWrapper {
  list-style-type: none;
  margin: 0;
  padding: 10px;
  border-radius: 5px;
  background-color: gainsboro;
  width: 100%;
  height: 100%;
  min-height: 300px;
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.didNotThing {
  background-color: white;
}

.didThing {
  background-color: aquamarine;
}

.task {
  margin: 0;
  padding: 15px;
  display: flex;
  flex-direction: row;
  height: 40px;
  align-items: center;
  justify-content: space-between;
  font-size: medium;
  font-weight: bold;
}

.Form {
  width: 100%;
  height: 30px;
  display: flex;
  gap: 5px;
  padding: 0px 20px;
}

.Form-Text {
  width: 100%;
  border-color: gainsboro;
  border-radius: 5px;
}

.AddButton {
  background-color: blue;
  border: blue;
  color: white;
  font-size: small;
  align-self: center;
  justify-self: center;
  border-radius: 8px;
  height: 100%;
  width: 50px;
}

@media (max-width: 768px) {
  .parent {
    padding: 50px;
  }

  .title {
    font-size: 30px;
  }
  .allWrapper {
    gap: 20px;
    width: 100%;
    height: 100%;
    margin: 0;
  }

  .task {
    font-size: small;
  }
}
</style>
