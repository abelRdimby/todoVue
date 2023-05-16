<template>
  <div class="myAppViewer">
    <HeaderOfApp
      nameApp="Todo List"
      :searchQuery="searchQuery"
      @update:searchQuery="updatedSearchQuery"
      @search-updated="filterDataArray"
    />
    <TodoViewer
      itemName="Items Name"
      :dataArray="filteredArray"
      @data-updated="updateDataArray"
    />
    <FooterOfApp @todo-added="addNewTodo" />
  </div>
</template>

<script>
import HeaderOfApp from './components/Header.vue';
import TodoViewer from './components/TodoViewer.vue';
import FooterOfApp from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    HeaderOfApp,
    TodoViewer,
    FooterOfApp,
  },
  data() {
    return {
      tableauRécupéré: [],
      searchQuery: '',
      filteredArray: [],
    };
  },


  mounted() {
    let tableauString = localStorage.getItem('tableau');
    if (tableauString) {
      this.tableauRécupéré = JSON.parse(tableauString);
    }else {
      this.tableauRécupéré = [
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
      ]
    this.saveArray();
    }
    this.filterDataArray();
  },

  methods: {
    addNewTodo (newTodo) {
      this.tableauRécupéré.push(newTodo);
      this.saveArray();
      console.log(this.tableauRécupéré);
    },
    saveArray() {
      var tableauString = JSON.stringify(this.tableauRécupéré);
      localStorage.setItem('tableau', tableauString);
    },
    sendData() {
      const dataArray = this.tableauRécupéré;
      this.$emit('data-updated', dataArray);
    },
    updateDataArray(newDataArray) {
      this.tableauRécupéré = newDataArray;
    },
    updatedSearchQuery(query) {
      this.searchQuery = query;
      this.filterDataArray();
    },
    filterDataArray() {
      this.filteredArray = this.tableauRécupéré.filter(item => {
        return item.name.toLowerCase().includes(this.searchQuery.toLowerCase());
      });
    },
  },
};
</script>

<style lang="scss">
#app {
  font-family: 'Urbanist', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: var(--grey);
  width: 290px;
  height: 548px;
  overflow: hidden;
  background-color: var(--white);
  input {
    font-family: 'Urbanist', sans-serif;
    letter-spacing: 1px;
  }
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
