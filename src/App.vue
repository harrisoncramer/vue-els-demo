<script setup>
import { default as Harvest2 } from './components/Harvest2.vue';
import { default as Harvest3 } from './components/Harvest3.vue';
import { default as Harvest3Setup } from './components/Harvest3Setup.vue';

const seeds = [ "🍈", "🍉", "🍊", "🍋", "🍌", "🍍", "🥭", "🍎", "🍏", "🍐", "🍑", "🍒", "🍓", "🫐", "🥝", "🍅", "🫒", "🥥", "🥑", "🍆", "🥔", "🥕", "🌽", "🌶️", "🫑", "🥒", "🥬", "🥦", "🧄", "🧅", "🍄", "🥜", "🍞", "🥐", "🥖", "🫓", "🥨", "🥯", "🥞", "🧇", "🧀", "🍖", "🍗", "🥩", "🥓", "🍔", "🍟", "🍕", "🌭", "🥪", "🌮", "🌯", ];

const crop = 'setup'

</script>
<template>
  <Harvest2 v-if="crop === 2" :seeds="seeds"/>
  <Harvest3 v-else-if="crop === 3" :seeds="seeds"/>
  <Harvest3Setup v-else-if="crop === 'setup'" :seeds="seeds"/>
</template>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
