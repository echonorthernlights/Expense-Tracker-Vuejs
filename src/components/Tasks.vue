<template>
  <div :key="task.id" v-for="task in tasks">
    <Task
      @toggle-task="$emit('toggle-task', task.id)"
      @delete-task="$emit('delete-task', task.id)"
      :task="task"
    />
  </div>
</template>

<script>
import Task from "./Task.vue";
export default {
  name: "Tasks",
  components: {
    Task,
  },
  props: {
    tasks: Array,
  },
  emits: ["delete-task", "toggle-task"],
};
</script>
