<template>
  <div class="modal">
    <div v-if="uiState === 'won'">
        <h2>You won</h2>
    </div>
    <div v-else>
        <h2>You lost</h2>
    </div>
    <p>
      <button @click="restart">Let's play again!</button>
    </p>
  </div>
</template>

<script>
  import { mapState } from "vuex"

  export default {
    computed: {
      ...mapState("uiState")
    },
    methods: {
      restart() {
        this.$store.commit("restartGame")
      }
    }
  }
</script>

<style lang="scss" scoped>

</style>