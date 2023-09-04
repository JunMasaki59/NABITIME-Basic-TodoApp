<script setup>
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
</script>

<template>
  <div class="parent">
    <div class="allWrapper">
      <h1 class="title">ToDo</h1>
      <ul class="toDoListWrapper">
        <li class="toDoThing">
          <label class="task"> 期末試験 <input type="checkbox" name="toDo" class="checkbox" /> </label>
        </li>
        <li class="toDoThing">
          <label class="task"> 宿題 <input type="checkbox" name="toDo" class="checkbox" /> </label>
        </li>
      </ul>
      <div class="Form">
        <input type="text" name="addToDo" class="Form-Text" />
        <input type="button" value="追加" name="AddButton" class="AddButton" />
      </div>
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
  margin: 0;
  padding: 70px;
  height: 100%;
}
.allWrapper {
  display: flex;
  flex-direction: column;
  gap: 20px;
  width: 100%;
  height: 100%;
  margin: 0;
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

.toDoThing {
  width: 100%;
}

.task {
  margin: 0;
  padding: 15px;
  display: flex;
  flex-direction: row;
  background-color: white;
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
