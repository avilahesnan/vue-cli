<template>
  <div>
    <h1>Clicado {{ contador }} vezes</h1>
    <button @click="incrementar">Incrementar</button>
  </div>
</template>

<script>
export default {
  data () {
    return {
      contador: 0
    }
  },
  methods: {
    incrementar () {
      this.contador++
    }
  }
}
</script>
