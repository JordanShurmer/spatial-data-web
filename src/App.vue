<template>
  <div id="app">

    <!--<aside>-->
      <!--<h1>The Data</h1>-->
<!---->
      <!--<nav class="the-controls">-->
        <!--<the-controls/>-->
      <!--</nav>-->
    <!--</aside>-->

    <main>
      <breeding-rhombus-spinner
        v-if="loading"
        :animation-duration="2000"
        :size="65"
        :color="'#ff1d5e'"
      />
      <the-map v-else/>
    </main>

  </div>
</template>

<script>
  import TheMap from "./components/TheMap";
  import TheControls from "./components/TheControls";
  import HollowDotsSpinner from "epic-spinners/src/components/lib/HollowDotsSpinner";
  import BreedingRhombusSpinner from "epic-spinners/src/components/lib/BreedingRhombusSpinner";

  export default {
    components: {
      BreedingRhombusSpinner,
      HollowDotsSpinner,
      TheControls,
      TheMap
    },
    name: 'app',
    data() {
      return {
        loading: false,
      }
    },
    async created() {
      // await this.$store.dispatch('init');
      this.$nextTick(() => this.loading = false);
    }
  }
</script>


<style lang="scss">

  @import "~pretty-checkbox/src/pretty-checkbox.scss";

  #app {
    position: absolute;
    height: 100vh;
    width: 100%;
    display: flex;
    flex-flow: row nowrap;

    aside {
      width: 33%;
      height: 100%;
    }

    main {
      flex: 1 1 100%;
      height: 100%;
    }
  }

  /*Some global styles*/
  body {
    font-family: 'Roboto Condensed', sans-serif;
    margin: 0;
  }

  h1, h2 {
    font-weight: normal;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }

</style>
