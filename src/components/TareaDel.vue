<template>
  <div>
    <h1 class="taskListTitle">Lista</h1>
    <ol>
      <li v-for="(Task, index) in Tasks" :key="index">
        {{ Task }}<button class="btnDelete" @click="delTask(Tasks)">Eliminar</button>
      </li>
    </ol>
  </div>
</template>

<script>
export default {
  name: "TaskDel",
  props: {
    Tasks: {
      type: Array,
      required: true,
    },
  },
  methods :{
  delTask(Tasks) {
    this.$emit("deleteTask", Tasks)
  },
  }
};
</script>
