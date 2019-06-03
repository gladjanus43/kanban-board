<template>
  <div class="row">
    <div class="scroll">
      <div v-bind:key="card.id" v-for="card in cards">
        <Card
          v-bind:card="card"
          v-if="status == card.status"
          v-on:update-status="updateStatus"
        />
      </div>
    </div>
  </div>
</template>

<script>
import Card from "./Card";

export default {
  name: "CardRow",
  components: {
    Card
  },
  props: ["cards", "status"],
  data(){
      return {

      }
  },
  methods: {
      updateStatus(object){
        this.$emit('update-status', object)
      }
  }
};
</script>

<style scoped>
.row {
  min-width: 400px;
  max-width: 400px;
  height: 100%;
  background-color: white;
  border-radius: 20px;
  margin: 0 10px 0 10px;
}
</style>
