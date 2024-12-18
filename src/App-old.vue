<script setup>
import { computed, onMounted, ref } from 'vue'

const name = ref('Olívia Faria')
const status = ref('active')
const tasks = ref(['Task One', 'Task Two', 'Task Three'])
const link = ref('https://google.com')
const newTask = ref('')

const message = computed(() => `User ${name.value} status is: ${status.value}`)

const toggleStatus = () => {
  if (status.value === 'active') {
    status.value = 'pending'
  } else if (status.value === 'pending') {
    status.value = 'inactive'
  } else {
    status.value = 'active'
  }
}

const addTask = () => {
  if (newTask.value.trim() !== '') {
    tasks.value.push(newTask.value)
    newTask.value = ''
  }
}

const deleteTask = index => {
  tasks.value.splice(index, 1)
}

onMounted(async () => {
  try {
    const response = await fetch('https://jsonplaceholder.typicode.com/todos')
    const data = await response.json()
    tasks.value = data.map(task => task.title)
  } catch (error) {
    console.error('Error fetching tasks!', error)
  }
})
</script>

<template>
  <h1>{{ name }}</h1>
  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>User is inactive</p>

  <h3>Tasks</h3>

  <form @submit.prevent="addTask">
    <input v-model="newTask" type="text" id="newTask" name="newTask" placeholder="Add new task" />
    <button type="submit">Add</button>
  </form>

  <ul>
    <li v-for="(task, index) in tasks" :key="task">
      <span>
        {{ task }}
      </span>

      <button @click="deleteTask(index)">X</button>
    </li>
  </ul>

  <a :href="link">Go to Google</a>

  <button @click="toggleStatus">Change status</button>

  <p>{{ message }}</p>
</template>

<style scoped>
h1,
p,
button {
  display: block;
}

ul {
  margin-block: 2rem;
  padding-inline: 0;
}

li {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
}
</style>
