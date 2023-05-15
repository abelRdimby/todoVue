<template>
    <div class="items" v-for="(u, index) in tableauRécupéré"
      :key="`u-${index}`"
      :data= "u">
        <div class="itemBox">
          <input class="checkBox" type="checkbox">
        </div>
        <div class="itemName">
          <p>{{ u.name }}</p>
        </div>
        <div class="itemBox">
          
          <a href="/">
            <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-trash" width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                        <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                        <path d="M4 7l16 0"></path>
                        <path d="M10 11l0 6"></path>
                        <path d="M14 11l0 6"></path>
                        <path d="M5 7l1 12a2 2 0 0 0 2 2h8a2 2 0 0 0 2 -2l1 -12"></path>
                        <path d="M9 7v-3a1 1 0 0 1 1 -1h4a1 1 0 0 1 1 1v3"></path>
            </svg>
          </a>

        </div>
      </div>
</template>
<script>
export default {
    name: "TodoCard",
    data() {
        return {
            todoCard: [],
        }
    }
}
</script>
<style scoped>
  .items {
    border: 1px var(--grey) solid;
    color: var(--black);
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    padding: 0;
    margin: 0;
    height: 67px;
  }
  .itemBox {
    width: 55px;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;

  }
  .itemName {
    width: 58%;
    height: 100%;
    display: flex;
    justify-content: start;
    align-items: center;
  }
.checkBox {
      border: var(--grey) 2px solid;
    }
svg {
  color: var(--red);
}
</style>