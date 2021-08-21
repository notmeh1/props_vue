<template>
  <div class="container">
    <div class="taskCard">
      <label class="taskTitle">Tareas</label>
      <input
        class="taskInput"
        type="text"
        v-model="newTask"
        placeholder="Ingresa una nueva tarea"
      />
      <button class="btnAdd" @click="addNewTask">Agregar</button>
      <TareaDel :Tasks="Tasks" @deleteTask="deleteTask"/>
    </div>
  </div>
</template>

<script>
import TareaDel from "./TareaDel.vue";
export default {
  name: "Tasks",
  components: {
    TareaDel,
  },
  data: () => ({
    newTask: "",
    Tasks: ["Despertar"],
  }),
  methods: {
    addNewTask() {
      this.Tasks.push(this.newTask);
      this.newTask = "";
    },
    deleteTask(Tasks) {
        this.Tasks.splice(Tasks, 1)
    }
  },
};
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.taskCard {
  background-color: #2d3848;
  border-radius: 20px;
  padding: 2em 1em;
  margin-top: 2em;
  box-shadow: 5px 8px 15px -6px #000000;
}
.taskCard * {
  margin: 0 0.3em 1em 0.3em;
  color: #ffffff;
}
.taskInput {
  color: #000000;
  border: 1px;
  padding: 3px;
}
.taskInput:focus {
  outline: none;
}
.btnAdd {
  padding: 5px 7px;
  background-color: #3399ff;
  border: 0;
  cursor: pointer;
  transition: background-color 0.3s;
}
.btnAdd:hover {
  background-color: #0080ff;
}
.btnAdd:active {
  background-color: #0066cc;
}
.taskListTitle {
  text-align: center;
  margin-bottom: 0.3em;
}
.taskListNT {
    text-align: center;
}
.btnDelete {
  padding: 5px 7px;
  background-color: #f93e3e;
  border: 0;
  cursor: pointer;
  transition: background-color 0.3s;
}
.btnDelete:hover {
  background-color: #f70808;
}
.btnDelete:active {
  background-color: #c60606;
}
</style>
