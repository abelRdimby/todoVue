<script>
export default {
  name: 'HeaderOfApp',
  props: {
    nameApp: String,
    finderTag: String,
  }
}
</script>

<template>
  <div class="header">
    <div class="appTitle">
      <h1>{{ nameApp }}</h1>
    </div>
    <div class="inputContainer">
      <div class="searchSection">
          <a href="/">
            <div class="searchIcon">
            <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-search" width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                        <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                        <path d="M10 10m-7 0a7 7 0 1 0 14 0a7 7 0 1 0 -14 0"></path>
                        <path d="M21 21l-6 -6"></path>
            </svg>
            </div>
          </a>
        <input class="searchInput" type="text" placeholder="Search Todo">
      </div>
      
    </div>
  </div>
</template>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped >
.header {
  width: 290px;
  color: var(--grey);
  .appTitle{
    display: flex;
    align-items: center;
    background-color: var(--blue) ;
    color: var(--white);
    height: 65px;
    padding-inline: 20px;
  }
  .inputContainer {
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 5 0 20px;
    width: 100%;
    height: 75px;
  }
  .searchSection {
    position: relative;
    border-radius: 6px;
    overflow: hidden;
  }
  .searchIcon {
    position: absolute;
    right: 0;
    width: 50px;
    height: 100%;
    background-color: var(--grey);
    display: flex;
    align-items: center;
    justify-content: center;
    // opacity: 25%;
  }
}
.searchIcon svg{
    color: rgb(63, 63, 63);
    height: 50px;
    width: 30px;
  }
.searchInput{
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
h1{
    font-size: 25px;
    font-weight: 500;
    text-align: center;
}
// h3 {
//   margin: 40px 0 0;
// }
// ul {
//   list-style-type: none;
//   padding: 0;
// }
// li {
//   display: inline-block;
//   margin: 0 10px;
// }
// a {
//   color: #42b983;
// }
</style>
