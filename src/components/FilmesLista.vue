<template>
  <div class="row">

    <!-- coluna 1 -->
    <div class="col-8">

      <h2>Filmes</h2>

      <ul class="list-group list-group-flush">

        <FilmesListaItem
        v-for="filme in filmes"
        :key="filme.id"
        :filme="filme"
        @selecionarFilme="filmeSelecionado = $event"/>

      </ul>
    </div>

    <!-- coluna 2 -->
    <div class="col-4">

      <FilmesListaItemInfo
      v-if="!editar"
      :filme="filmeSelecionado"
      @editarFilme="editarFilme"/>

      <FilmesListaItemEditar
      v-else
      :filme="filmeSelecionado"/>

    </div>

  </div>
</template>

<script>

import FilmesListaItem from './FilmesListaItem.vue'
import FilmesListaItemEditar from './FilmesListaItemEditar.vue'
import FilmesListaItemInfo from './FilmesListaItemInfo.vue'

export default {
  components: {
    FilmesListaItem,
    FilmesListaItemEditar,
    FilmesListaItemInfo
  },
  data () {
    return {
      filmes: [
        { id: 1, titulo: 'Vingadores: Guerra Infinita', ano: 2018 },
        { id: 2, titulo: 'Deadpool', ano: 2016 },
        { id: 3, titulo: 'Deadpool 2', ano: 2022 }
      ],
      filmeSelecionado: undefined,
      editar: false
    }
  },
  methods: {
    editarFilme (filme) {
      this.editar = true
      this.filmeSelecionado = filme
    }
  }
}
</script>
