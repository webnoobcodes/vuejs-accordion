<template>
  <div id="app">
    <List />
  </div>
</template>

<script>
  import List from "./components/List";

  export default {
    components: {
      List
    }
  };
</script>

<style lang="scss">
  @import url("https://use.fontawesome.com/releases/v5.11.0/css/all.css");
  @import url("https://fonts.googleapis.com/css?family=Oswald");

  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  body {
    font-size: 1rem;
    font-family: "Oswald", Tahoma;
    background-color: #86bb89;
    color: #333;
  }

  #app {
    position: relative;
    padding: 10px;
    min-height: 100vh;
    width: 100%;
  }
</style>
