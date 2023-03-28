<template>
  <div id="app">
    <TasksListVue />
  </div>
</template>
<script>
  import TasksListVue from './components/TasksList.vue';
  export default {
    name: "App",
    components: {
      TasksListVue,
    },
  };
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>