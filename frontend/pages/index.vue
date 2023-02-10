<template>
  <v-layout justify-center align-center>
    <!-- <v-btn color="success" :to="{name: 'Notas'}">Notas</v-btn> -->
    <router-link :to="'notas'">Notas</router-link>
  </v-layout>
</template>

<script>

export default {
  data () {
    return {}
  }
}
</script>

<style>
</style>