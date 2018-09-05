<template>
  <div class="game">
    <div v-for="column in gridSize" class="grid-column">
      <div v-for="row in column" class="grid-row" v-bind:class="getCellValue(row, column)">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Snake',
    props: {
        gridSize: 32,
    },
    created: {
},
methods: {
    getCellValue(r, c) {
        let cellValue;
        if (r === 2 && c === 3) {
            cellValue = 'snake1';
        }
        return cellValue;
    },
    handleKeydown(e) {
        console.log(e);
    },

},
mounted() {
    window.addEventListener('keydown', e => {
        console.log(e);
    });
},
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .game {
    height: 704px;
    width: 704px;
    display: flex;
    border: 2px solid black;
  }

  .grid-column {
  }

  .grid-row {
    width: 20px;
    height: 20px;
    border: 1px solid #aacccc;
    background-color: #cccccc;
  }

  .snake {
    background-color: red;
  }
</style>
