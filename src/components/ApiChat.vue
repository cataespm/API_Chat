<script>
import axios from 'axios'

export default {
  name: 'ApiChat',
  setup() {},
  beforeCreate() {},
  data() {
    return {
      variableEstado: 'Nuestro compenente LifeCycle',
      usuarioA: {},
      usuarioB: {}
    }
  },
  created() {},
  beforeMount() {},
  async mounted() {
    console.log('En montado, aquí ya se ve en el documento')
    const url = 'https://randomuser.me/api/?results=2'
    const { data } = await axios.get(url)

    this.users = data.results
    this.usuarioA = this.users[0]
    this.usuarioB = this.users[1]
  }
}
</script>
<template>
  <div class="card" style="width: 18rem">
    <img :src="usuarioA?.picture?.large" class="card-img-top" alt="..." />
    <div class="card-body">
      <h5 class="card-title">
        {{ usuarioA.name.title }}
        {{ usuarioA.name.first }}
        {{ usuarioA.name.last }}
      </h5>
      <p class="card-text">
        Some quick example text to build on the card title and make up the bulk of the card's
        content.
      </p>
      <a href="#" class="btn btn-primary">Go somewhere</a>
    </div>
  </div>

  <div>CHAT</div>

  <div class="card" style="width: 18rem">
    <img :src="usuarioB?.picture?.large" class="card-img-top" alt="..." />
    <div class="card-body">
      <h5 class="card-title">
        {{ usuarioA.name.title }}
        {{ usuarioA.name.first }}
        {{ usuarioA.name.last }}
      </h5>
      <p class="card-text">
        Some quick example text to build on the card title and make up the bulk of the card's
        content.
      </p>
      <a href="#" class="btn btn-primary">Go somewhere</a>
    </div>
  </div>

  <h1>ApiChat</h1>
</template>
