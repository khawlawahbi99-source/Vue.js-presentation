<template>
    <div class="todo-form">
        <input type="text" v-model = "newTask" placeholder="Ajouter une tâche...">
        <button @click ="submitTask">Ajouter</button>
    </div>
</template>

<script>
export default {
    emits: ['add-task'],
    data() {
        return {
            newTask: ''
        }
    },

    methods: {
        submitTask() {
            if (this.newTask.trim() === '')
            return
            this.$emit('add-task',this.newTask.trim())
            this.newTask = '';
        }
    }
}
</script>

<style scoped>
.todo-form {
  display: flex;
  gap: 10px;
  margin-bottom: 20px;
}

.todo-form input {
  flex: 1;
  padding: 10px;
  border: 2px solid #ddd;
  border-radius: 8px;
  font-size: 14px;
  outline: none;
}

.todo-form input:focus {
  border-color: #3498db;
}

.todo-form button {
  padding: 10px 16px;
  background-color: #3498db;
  color: white;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  font-size: 14px;
}

.todo-form button:hover {
  background-color: #2980b9;
}
</style>