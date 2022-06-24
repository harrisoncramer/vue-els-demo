<template>
  <form @submit.prevent="onSubmit">
    <label>Who is harvesting the crops? </label>
    <br style="margin-bottom: 10px;"/>
    <input v-model="message" name=""/>
    <button>Harvest</button>
  </form>
  <h2>{{ message ?? "Nobody" }} is ready to harvest...</h2>
  <div style="font-size: 48px;" v-if="crop">
      <FoodWrapper> {{ crop }}</FoodWrapper>
  </div>
</template>

<script setup>
import FoodWrapper from "./FoodWrapper.vue"
import { ref, onMounted, defineProps } from "vue"

onMounted(() => alert("Let's grow some crops, broh"))

const props = defineProps({
  seeds: {
    type: Array,
    required: true,
    default: () => []
  }
})

const message = ref(null);
const crop = ref(null);

function onSubmit () {
  const seedIndex = Math.floor(Math.random() * props.seeds.length)
  crop.value = props.seeds[seedIndex];
}

</script>
