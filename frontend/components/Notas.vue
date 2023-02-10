<template>
  <v-layout justify-center align-center>
      <v-data-table
        :headers="headers"
        :items="notas"
        :items-per-page="5"
        class="elevation-1"
      >
        <template slot="items" slot-scope="props">
            <td>{{ props.item.name}}</td>
            <td class="text-xs-right">{{ props.item.countnotas }}</td>
            <td class="text-xs-right">{{ props.item.maisantiga }}</td>
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
            { text: 'Nome', value: 'name' },
            { text: 'Quantidade de notas', value: 'countnotas' },
            { text: 'Mais Antiga', value: 'maisantiga' },
        ]
    }
  },
  created(){
    AppApi.list_notas().then(response => {
        this.notas = response.data
    })
  }
}
</script>

<style>
</style>