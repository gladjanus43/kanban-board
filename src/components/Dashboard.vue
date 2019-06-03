<template>
  <div class="board">
    <CardRow status="0" v-bind:cards="cards" v-on:update-status="updateStatus"/>
    <CardRow status="1" v-bind:cards="cards" v-on:update-status="updateStatus"/>
    <CardRow status="2" v-bind:cards="cards" v-on:update-status="updateStatus"/>
  </div>
</template>

<script>
import CardRow from "./CardRow";
import { stat } from 'fs';
export default {
  name: "Dashboard",
  components: {
    CardRow
  },
  data() {
    return {
      cards: [
        {
          id: 1,
          titel: "Order Gijs Bijvoets",
          description: "Dit is een order",
          status: 1
        },
        {
          id: 2,
          titel: "Order Henk Nog iets",
          description: "Dit is er ook een",
          status: 0
        },
        {
          id: 3,
          titel: "Order Met Wat extra",
          description: "Ik niet hoor!",
          status: 2
        }
      ]
    };
  },
  methods: {
    updateStatus(object){
      for(let i = 0; i < this.cards.length; i++){
        if(this.cards[i].id == object.id){
          this.cards[i].status = Number(object.status)
        }
      }
    }
  }
};
</script>

<style scoped>
.board {
  width: 100vw;
  height: 100vh;
  background-color: beige;
  display: flex;
  justify-content: center;
  padding: 20px 0 20px 0;
}
</style>
