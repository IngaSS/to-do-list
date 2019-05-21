<template>
  <div class="list row justify-content-space-around">
    <Task v-for="task in tasks" :key="task.name" :task="task" :dropTask="dropTask"></Task>
  </div>
</template>

<script>
import Task from "./Task";
export default {
  name: "TaskList",
  props: ["tasks", "dropTask"],
  components: {
    Task
  }
};
</script>

<style>
.list {
  margin-top: 20px;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  max-width: 100%;
  margin: 20px auto;
}
</style>

