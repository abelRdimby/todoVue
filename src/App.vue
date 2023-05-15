<template>
<div class="myAppViewer">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <HeaderOfApp nameApp="Todo List"/>
    <TodoViewer itemName="Items Name" :dataArray="tableauRécupéré"/>
    <FooterOfApp/>
</div>
</template>

<script>
import HeaderOfApp from './components/Header.vue'
import TodoViewer from './components/TodoViewer.vue'
import FooterOfApp from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    HeaderOfApp,
    TodoViewer,
    FooterOfApp,
  },
  // methods: {
  //   handleData(dataArray) {
  //     console.log(dataArray)
  //   },
  //   isValid() {
  //     const newTodo = document.getElementById('inputNewTodo').value;
  //     if(newTodo === "") {
  //       return false
  //     }
  //   }

  // },
  // mounted() {
  //   this.isValid()
  //   console.log(this.newTodo)
  // }

  data() {
    return {
      tableauRécupéré: [],
    };
  },

  mounted() {
    let tableauString = localStorage.getItem('tableau');
    if (tableauString) {
      this.tableauRécupéré = JSON.parse(tableauString);
    }
    this.saveArray();
    this.sendData();
  },

  methods: {
    saveArray() {
      var monTableau = [
        {
          name: 'Todo 01',
          id: 1,
        },
        {
          name: 'Todo 02',
          id: 2,
        },
        {
          name: 'Todo 03',
          id: 3,
        },
        {
          name: 'Todo 04',
          id: 4,
        },
        {
          name: 'Todo 05',
          id: 5,
        },
        {
          name: 'Todo 06',
          id: 6,
        },
      ];
      var tableauString = JSON.stringify(monTableau);
      localStorage.setItem('tableau', tableauString);
    },
    sendData() {
      const dataArray = this.tableauRécupéré;
      this.$emit('data-updated', dataArray);
    },
  },

  watch: {
    tableauRécupéré: {
      handler() {
        this.saveArray();
      },
      deep: true,
    },
  },
}
</script>

<style lang="scss">
#app {
  font-family: 'Red Hat Text', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: var(--grey);
  width: 290px;
  height: 548px;
  overflow: hidden;
  background-color: var(--white);
  .myAppViewer {
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
  }
}
</style>
