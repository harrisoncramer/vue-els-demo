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

<script>
import FoodWrapper from "./FoodWrapper.vue"
import { ref, onMounted } from "vue"

export default {
  name: "Vue 3",
  components: {
    FoodWrapper
  },
  props: {
    seeds: {
      type: Array, 
      required: true,
      default: () => [],
    }
  },
  setup (props) {
    const message = ref(null);
    const crop = ref(null);

    onMounted(() => alert("Let's grow some crops, broh"))

    function onSubmit () {
      const seedIndex = Math.floor(Math.random() * props.seeds.length)
      crop.value = props.seeds[seedIndex];
    }

    return { onSubmit, message, crop }
  }
}
</script>
