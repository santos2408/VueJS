<script>
  export default {
      data() { 
        return {
          title: 'Diretiva v-bind',
          headerClass: { 'background-color': 'purple', 'color': 'white' },
          todos: [
            {
              "userId": 1,
              "id": 1,
              "title": "House Stark",
              "completed": false,
              "url": "https://thronesapi.com/assets/images/jon-snow.jpg",
            },
            {
              "userId": 1,
              "id": 2,
              "title": "House Targaryen",
              "completed": false,
              "url": "https://thronesapi.com/assets/images/daenerys.jpg",
            },
            {
              "userId": 1,
              "id": 3,
              "title": "House Lannister",
              "completed": false,
              "url": "https://thronesapi.com/assets/images/jaime-lannister.jpg",
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
          ],
          personagem: null,
          data: {
            conteudo: 'conteudo do objeto data'
          },
          fundoSelecionado: null
        }
      }
    }
</script>

<template>
  <footer :style="{ backgroundColor: fundoSelecionado }">
    <h1 :style="headerClass">{{ title }}</h1>
    <h1>{{ data.conteudo }}</h1>

    <input v-model="fundoSelecionado" type="color">

    <ul>
      <li v-for="(obj, index) in todos" v-bind:key="obj.id">
        <img
          width="160"
          
          v-if="obj.url"
          v-bind:src="obj.url"
          v-bind:alt="obj.title">

        {{ index }} - {{ obj.title }} | {{ obj.id }}
      </li>
    </ul>

    <select v-model="personagem">
      <option value="">Escolha:</option>
      <option value="Jame Lannister">Jame Lannister</option>
      <option value="John Snow">John Snow</option>
      <option value="Daenerys Targaryen">Daenerys Targaryen</option>
    </select>
    <p v-if="personagem">Você escolheu: {{ personagem }}</p>
  </footer>
</template>

<style scoped>
.section-header {
  color: green;
}

.classe-invalida {
  color: red;
}
</style>
