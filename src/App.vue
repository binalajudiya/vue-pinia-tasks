<template>
  <main>
    <!-- heading -->
    <header>
      <h1>Pinia Tasks</h1>
    </header>

    <!-- new task form -->
    <div class="new-task-form"></div>

    <!-- filter -->
    <nav class="filter">
      <button @click="filter = 'all'">All tasks</button>
      <button @click="filter = 'favs'">Fav tasks</button>
    </nav>

    <!-- loading -->

    <!-- task list -->
    <div class="task-list">
      <p>You have {{ taskStore.favCount }} tasks in your favs list.</p>
      <div v-for="task in taskStore.tasks" :key="task.id">
        {{ task.title }}
      </div>
    </div>
  </main>
</template>

<script>
import { useTaskStore } from "@/stores/TaskStore";

export default {
  setup() {
    const taskStore = useTaskStore();

    const filter = ref("all");

    return { taskStore };
  },
};
</script>
