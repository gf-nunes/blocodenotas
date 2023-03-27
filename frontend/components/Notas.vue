<template>
  <v-layout justify-center align-center>
      <v-data-table
        :headers="headers"
        :items="notas"
        :items-per-page="5"
        class="elevation-1"
      >
        <template slot="items" slot-scope="props">
            <td>{{ props.item.description}}</td>
        </template>
      </v-data-table>
  </v-layout>
</template>

<script>
import Notas from '~/components/Notas.vue'
import AppApi from '~apijs'

export default {
  data () {
    return {
        notas:[],
        headers: [
            { text: 'Notas', value: 'name' },
            // { text: 'Quantidade de notas', value: 'countnotas' },
            // { text: 'Mais Antiga', value: 'maisantiga' },
        ]
    }
  },
  created(){
    AppApi.list_todos().then(response => {
        this.notas = response.data['todos']
    })
  }
}
</script>

<style>
</style>