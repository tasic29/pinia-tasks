<template>
  <div class="task">
    <h3>{{ task.title }}</h3>
    <div class="icons">
      <i @click="taskStore.deleteTask(task.id)" class="material-icons"
        >delete</i
      >
      <i
        @click="taskStore.toogleFav(task.id)"
        :class="{ active: task.isFav }"
        class="material-icons"
        >favorite</i
      >
    </div>
  </div>
</template>

<script>
import { useTaskStore } from "@/stores/TaskStore";
export default {
  props: ["task"],
  setup() {
    const taskStore = useTaskStore();

    return {
      taskStore,
    };
  },
};
</script>
