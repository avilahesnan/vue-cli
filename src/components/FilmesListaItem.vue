<template>
    <li class="list-group-item">
        <span>{{ filme.titulo }} | {{ filme.ano }}</span>
        <button @click="selecionar" class="btn btn-success float-end">Selecionar</button>
    </li>
</template>

<script>

import { eventBus } from '../main'

export default {
  props: {
    filme: {
      type: Object,
      required: true
    }
  },
  methods: {
    selecionar (event) {
      eventBus.$emit('selecionarFilme', this.filme)
    }
  }
}
</script>
