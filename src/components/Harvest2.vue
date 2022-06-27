<template>
  <div>
    <form @submit.prevent="onSubmit">
      <label>Who is harvesting the crops? </label>
      <br style="margin-bottom: 10px;"/>
      <input v-model="message" name=""/>
      <button>Harvest</button>
    </form>
    <h2>{{ message ?? "Nobody" }} just grew...</h2>
    <div style="font-size: 48px;" v-if="crop">
      <FoodWrapper> {{ crop }}</FoodWrapper>
    </div>
  </div>
</template>

<script>
import FoodWrapper from "./FoodWrapper.vue"
export default {
  name: "Vue2",
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
  data () {
    return {
      message: null,
      crop: null,
    }
  },
  methods: {
    onSubmit () {
      const seedIndex = Math.floor(Math.random() * this.seeds.length)
      this.crop = this.seeds[seedIndex];
    }
  }
}
</script>
