<script>
  export default {
      data() { 
        return {
          todos: [
            {
              "userId": 1,
              "id": 1,
              "title": "House Stark",
              "completed": false
            },
            {
              "userId": 1,
              "id": 2,
              "title": "House Targaryen",
              "completed": false
            },
            {
              "userId": 1,
              "id": 3,
              "title": "House Lannister",
              "completed": false
            },
            {
              "userId": 1,
              "id": 4,
              "title": "House Blackwood",
              "completed": true
            },
            {
              "userId": 1,
              "id": 5,
              "title": "House Mormont",
              "completed": false
            }
          ]
        }
      }
    }
</script>

<template>
  <footer>
    <h1>Instruções de Loops</h1>

    <ul>
      <li v-for="(obj, index) in todos" v-bind:key="obj.id">
        {{ index }} - {{ obj.title }} | {{ obj.id }}
      </li>
    </ul>
  </footer>
</template>

<style scoped>
</style>
