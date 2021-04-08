<template>
  <div
    @dblclick="$emit('toggle-reminder', task.id)"
    :class="[task.reminder ? 'reminder' : 'todo', 'task']"
  >
    <h3>
      {{ task.text }}
      <i @click="$emit('delete-task', task.id)" class="fas fa-times"></i>
    </h3>
    <p>{{ task.day }}</p>
  </div>
</template>

<script>
export default {
  props: {
    task: Object,
  },
};
</script>

<style scoped>
.fas {
  color: crimson;
}
.task {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
  border-radius: 4px;
}
.task.reminder {
  border-left: 5px solid green;
}
.task.todo {
  border-left: 5px solid crimson;
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 5px;
}
</style>
