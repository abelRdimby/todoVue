<script>
export default {
  name: 'FooterOfApp',
  props: {
    nameApp: String,
    finderTag: String,
  },
  data() {
    return {
      newTodo: '',
    }
  },
  methods: {
    addTodo() {
      if(this.newTodo.trim() !== '') {

        const newTodoItem = {
          name: this.newTodo,
          id: Date.now(),
        };

        this.$emit('todo-added', newTodoItem)
        this.newTodo = ''
      }
      console.log('addTodo')
    },
  }
}
</script>

<template>
  
  <div class="footer">
    <div class="inputContainer">
      <div class="inputSection">
          <div class="addIcon">
            <a href="/" @click="addTodo">+Add</a>
        </div>
        <input class="addNewTodo" type="text" v-model.lazy="newTodo" placeholder="Add New Todo">
      </div>
      
    </div>
  </div>

</template>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
a {
  text-decoration: none;
}
.footer {
  width: 290px;
  color: var(--grey);
  .inputContainer {
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 5 0 20px;
    width: 100%;
    height: 89px;
    background-color: var(--grey-opacity-low);
  }
  .inputSection {
    position: relative;
    border-radius: 6px;
    overflow: hidden;
  }
  .addIcon {
    position: absolute;
    right: 0;
    width: 90px;
    height: 100%;
    background-color: var(--blue);
    display: flex;
    align-items: center;
    justify-content: center;
    // opacity: 25%;
  }
}
.addIcon a{
    color: var(--white);
    font-size: 20px;
    font-weight: bold;
  }
.addNewTodo{
    margin-block: auto;
    height: 45px;
    width: 250px;
    font-size: 18px;
    border-radius: 6px;
    border: none;
    outline: none;
    padding: 0 15px 0;
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
    border: 2px var(--grey) solid;
    color: var(--black);
    font-size: 18px;
  }
</style>
