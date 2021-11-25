<template>
	<div id="app">
    <Header />
    <Grid />
  </div>
</template>

<script>
import Grid from './components/Grid.vue';
import Header from './components/Header.vue';
export default {
	name: "App",
	components: {Header,Grid},
};
</script>

<style lang="scss">
*, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }
html,body {width: 100%; height: 100%; font-family: sans-serif; background: #1d2d3c;}
</style>
