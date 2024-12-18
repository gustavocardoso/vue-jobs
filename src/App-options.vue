<script>
export default {
  data() {
    return {
      name: 'Gustavo Cardoso',
      status: 'active',
      tasks: ['Task One', 'Task Two', 'Task Three'],
      link: 'https://google.com'
    }
  },
  computed: {
    message() {
      return `User ${this.name} status is: ${this.status}`
    }
  },
  methods: {
    toggleStatus() {
      if (this.status === 'active') {
        this.status = 'pending'
      } else if (this.status === 'pending') {
        this.status = 'inactive'
      } else {
        this.status = 'active'
      }
    }
  }
}
</script>

<template>
  <h1>{{ name }}</h1>
  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>User is inactive</p>

  <h3>Tasks</h3>
  <ul>
    <li v-for="task in tasks" :key="task">{{ task }}</li>
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
</style>
