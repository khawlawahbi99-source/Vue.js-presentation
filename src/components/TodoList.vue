<template>
   <div class = "todo-list">
    <todo-form @add-task = "addTask" />
    <p class = "empty" v-if="tasks.length === 0">Aucune tâche pour l'instant !</p>

    <transition-group name="fade" tag="div">
      <todo-item
       v-for="x in tasks"
       :key="x.id"
       :task="x"
       @toggle-task="toggleTask"
       @delete-task="deleteTask"
       />
    </transition-group>
   </div>  
</template>

<script>
import TodoForm from './TodoForm.vue'
import TodoItem from './TodoItem.vue'
export default {
  name: 'TodoList',
  components: { TodoForm, TodoItem },
    data() {
      return {
       tasks: []
  }
},

  mounted() {
  const saved = localStorage.getItem('tasks') 
  if (saved) {
    this.tasks = JSON.parse(saved)
  }
},

  watch: {
  tasks: {
    deep: true,
    handler(newTasks) {
      localStorage.setItem('tasks', JSON.stringify(newTasks))
    }
  }
},

    methods: {
        addTask(texte){
            this.tasks.push({ id:Date.now(), text: texte, done:false })
        },

        toggleTask(id){
            const task = this.tasks.find(t => t.id === id)
            if (task) 
            task.done = !task.done
        },

        deleteTask(id){
            this.tasks = this.tasks.filter(t => t.id !==id)

        }
    },
}
</script>

<style>
.fade-enter-active {
  transition: all 0.4s ease;
}
.fade-leave-active {
  transition: all 0.3s ease;
}
.fade-enter-from {
  opacity: 0;
  transform: translateX(-20px);
}
.fade-leave-to {
  opacity: 0;
  transform: translateX(20px);
}

.todo-list {
  background: white;
  border-radius: 12px;
  padding: 20px;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.empty {
  text-align: center;
  color: #aaa;
  margin-top: 20px;
}
</style>