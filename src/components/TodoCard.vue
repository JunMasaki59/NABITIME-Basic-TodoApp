<template>
  <div class="parent">
    <div class="allWrapper">
      <h1>ToDo</h1>
      <ul class="toDoListWrapper">
        <li class="toDoThing">
          <label> 期末試験 <input type="checkbox" name="toDo" class="checkbox" /> </label>
        </li>
        <li class="toDoThing">
          <label> 宿題 <input type="checkbox" name="toDo" class="checkbox" /> </label>
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
*{
  box-sizing: border-box;
}
.parent {
  margin: 0;
  padding: 20px;
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

h1 {
  margin: 0;
  text-align: center;
}

.toDoListWrapper {
  list-style-type: none;
  margin: 0;
  padding: 10px;
  background-color: gainsboro;
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 10px;
  height: 100%;
  border-radius: 5px;
}

.toDoThing {
  width: 100%;
}

label {
  margin: 0;  
  display: flex;
  flex-direction: row;
  padding: 5px;
  justify-content: space-between;
  background-color: white;
  height: 40px;
  align-items: center;
}

.Form {
  width: 100%;
  display: flex;
  gap: 5px;
  padding: 0px 5px;
}

.Form-Text {
  width: 100%;
  border-color: gainsboro;
  border-radius: 5px;
}

.AddButton{
  background-color: skyblue;
  border: skyblue;
  color: white;
  font-size: small;
  align-self: center;
  justify-self: center;
  border-radius: 5px;
}
</style>
