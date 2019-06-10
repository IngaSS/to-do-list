<template>
  <v-card class="task">
    <div class="taskArea">
      <h3>{{task}}</h3>
    </div>
    <div class="buttons">
      <v-checkbox class="done" color="success"></v-checkbox>
      <v-btn class="drop" @click="dropTask(task)">
        <v-icon class="drop-icon">block</v-icon>
      </v-btn>
    </div>
  </v-card>
</template>

<script>
export default {
  name: "Task",
  props: ["task", "dropTask"]
};
</script>

<style>
.task {
  width: 200px;
  min-height: 200px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  text-align: -webkit-center;
  margin-top: 10px;
}

.taskArea {
  text-align: justify;
  word-break: break-word;
  margin-top: 30px;
  text-align: justify;
  margin: 10px 5px;
}

.buttons {
  width: 150px;
  min-height: 30px;
  display: flex;
}

.done,
.drop {
  min-width: 10px;
}

.done {
  margin-top: 0;
}

.drop {
  background-color: transparent !important;
  box-shadow: none !important;
  height: 23px;
  border-radius: 25px;
  padding: 0;
}

.drop-icon {
  color: red !important;
}
</style>


