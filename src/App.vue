<template>
<div class="myAppViewer">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <HeaderOfApp nameApp="Todo List"/>
    <TodoViewer itemName="Items Name" @data-updated="handleData"/>
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
  methods: {
    handleData(dataArray) {
      console.log(dataArray)
    },
    isValid() {
      const newTodo = document.getElementById('inputNewTodo').value;
      if(newTodo === "") {
        return false
      }
    }

  },
  mounted() {
    this.isValid()
    console.log(this.newTodo)
  }
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
