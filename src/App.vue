<template>
  <TabsWrapper> 
    <tabSelect title="表頭1">我是表頭1</tabSelect>
    <tabSelect title="表頭2">我是表頭2</tabSelect>
    <tabSelect title="表頭3">我是表頭3</tabSelect>
  </TabsWrapper>
</template>

<script>
import TabsWrapper from "./components/TabsWrapper.vue";
import tabSelect from "./components/tabSelect.vue";
export default {
  name: "App",
  components: {
    TabsWrapper,
    tabSelect,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
</style>
