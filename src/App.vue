<template>
  <v-app class="mainArea">
    <v-card class="my-card">
      <v-text-field placeholder="Добавить задание" class="text-input" type="text" v-model="name" single-line
              outline clearable></v-text-field>
      <v-btn @click="addTask">Добавить</v-btn>
    </v-card>
    <TaskList :tasks="this.tasks" :dropTask="this.dropTask"></TaskList>
  </v-app>
</template>

<script>
import TaskList from "./components/TaskList";

export default {
  name: "App",
  components: {
    TaskList
  },
  data() {
    return {
      tasks: [],
      name: null
    };
  },
  methods: {
    addTask() {
      if (this.name != null && !this.tasks.includes(this.name)) {
        this.tasks.push(this.name);
      }
    },

    dropTask(task) {
      this.tasks.splice(this.tasks.indexOf(task), 1);
    }
  }
};
</script>

<style>
.mainArea {
  margin: auto;
}

.my-card {
  display: flex;
  flex-direction: column;
  min-height: 120px;
  width: 500px;
  border: 1px solid black;
  margin: 0 auto;
}

.text-input {
  max-width: 100%;
}

@media screen and (max-width: 500px) {
  .my-card {
    width: 100%;
  }
}
</style>

