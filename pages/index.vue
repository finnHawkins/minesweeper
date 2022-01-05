<template>
  <div>
    <nav class="navbar"></nav>
    <section class="controlsContainer">
      <div class="mineCounter">
        <p>{{ mineCounter }}</p>
      </div>
      <div class="newGame">
        <button @click="generateBoard()">New Game</button>
      </div>
      <div class="timer">
        <p>{{ timer }}</p>
      </div>
    </section>
    <div class="board">
      </div v-for="tile in board">
        <div
      <div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data: function () {
    return {
      board: [],
      timer: 0,
      mineCounter: 10,
    };
  },
  methods: {

    generateBoard() {

      var board = Array.from(Array(8), () => new Array(8));

      let minesToAdd = this.mineCounter;

      while(minesToAdd > 0) {

        //generate random coordinate for mine
        //make sure it's not already got a mine in it
        //if not, add mine
        //if so, regen coords

        let addedMine = false;

        while(!addedMine) {

          let x = Math.floor(Math.random() * 8);
          let y = Math.floor(Math.random() * 8);

          //alert(x + "," + y)

          if(board[x][y] !== -1) {

            board[x][y] = -1;
            addedMine = true;
            minesToAdd--;

          } else {


          }


        }

      }

      console.log(board);

    }

  }
};
</script>

<style lang="sass">

$width: 500px

.navbar
  height: 10px
  display: flex

.controlsContainer
  display: flex
  border: 1px solid black
  justify-content: space-evenly
  font-family: 'Consolas', monospace
  font-size: 20px
  align-items: center
  width: $width

  button
    font-family: 'Consolas', monospace
    font-size: 20px

  p
    font-weight: 900
    color: red
    padding: 2px

.board
  height: $width
  width: $width
  display: flex
  border: 1px solid black
  border-top: none
</style>
