<script>
export default {
  name: 'BtnClear',
  props: {
    btnName: String,
  }
}
</script>

<template>
  <div class="button">
    <a href="/">
      {{btnName}}
    </a>
  </div>

</template>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.button {
  width: 85%;
  height: 45px;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  margin-block: 20px;
}  
a {
  text-decoration: none;
  padding: 13px 7px;
  background-color: var(--black);
  border-radius: 4px;
  color: var(--white);
}
</style>
