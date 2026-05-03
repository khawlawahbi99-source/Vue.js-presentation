<template>
   <div class="todo-item" :class="{ done: task.done }">

    <input type = "checkbox" 
    :checked = "task.done"
    @change ="$emit('toggle-task', task.id)"/>
    <span>{{ task.text }}</span>
    <button @click = "$emit('delete-task', task.id)">🗑️</button>
   </div>
</template>

<script>
export default {
    name:'TodoItem',
    emits: ['toggle-task', 'delete-task'],
props:{
    task: Object
  },
}
</script>

<style scoped>
.todo-item {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 12px;
  border-radius: 8px;
  margin-bottom: 8px;
  background-color: #f8f9fa;
}

.todo-item.done span {
  text-decoration: line-through;
  color: #aaa;
}

.todo-item span {
  flex: 1;
  font-size: 15px;
}

.todo-item button {
  background: none;
  border: none;
  cursor: pointer;
  font-size: 18px;
}

.todo-item input[type="checkbox"] {
  width: 18px;
  height: 18px;
  cursor: pointer;
}
</style>