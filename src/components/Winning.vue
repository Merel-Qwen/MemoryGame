<template>
  <div class="win">
    <div>
      <h2>Congratulations!</h2>
      <ul class="stars">
        <li v-for="(star, index) in stars" :key="index">
          <i :class="`${index} fa fa-star`"></i>
        </li>
      </ul>
      <p>You won the game with {{stars}} stars left!</p>
      <button class="buttonGray" @click="newGame()">Play again</button>
    </div>
  </div>
</template>


<script>
import { mapState } from "vuex";

export default {
  name: "Winning",
  props: {
    newGame: { type: Function }
  },
  computed: {
    ...mapState(["stars"])
  }
};
</script>


<style lang="scss">
/* if you win */
.win {
  text-align: center;
  padding: auto;
  margin: auto;
}
.win h1 {
  font-weight: bold;
}
.win .stars {
  margin: 0;
  padding: 0;
  display: inline-block;
  margin: 0 5px 0 0;
}

.win .stars li {
  list-style: none;
  display: inline-block;
}
.win p {
  padding: 3em;
}
</style>
