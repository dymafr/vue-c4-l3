<template>
  <h1>Bonjour {{ user.prenom }}</h1>
  <h1>Compteur : {{ state.compteur }}</h1>
  <button @click="incCompteur()">+1</button>
</template>

<script setup lang="ts">
import { reactive, nextTick } from 'vue';

const state = reactive({
  user: { prenom: 'Jean', age: 21 },
  compteur: 0,
});

let {user} = state;

function incCompteur() {
  user.prenom = user.prenom === 'Jean' ? 'Paul' : 'Jean';
  state.compteur++;
  nextTick(() => {
    console.log('Tick');
  });
}
</script>

<style></style>
