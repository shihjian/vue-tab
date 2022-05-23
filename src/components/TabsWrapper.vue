<template>
  <div class="tabs">
    <ul class="tabs_header">
      <li
        :class="{ selected: title == selectedTitle }"
        v-for="title in tabTitle"
        :key="title"
        @click="selectedTitle = title"
      >
        {{ title }}
      </li>
    </ul>
    <slot />
  </div>
</template>
<script>
import { ref, provide } from "vue";
export default {
  setup(props, { slots }) {
    const tabTitle = ref(slots.default().map((item) => item.props.title));
    // 預設
    const selectedTitle = ref(tabTitle.value[0]);

    // 提供value給子元素
    provide("selectedTitle", selectedTitle);
    return {
      tabTitle,
      selectedTitle,
    };
  },
};
</script>

<style scoped>
.tabs {
  max-width: 400px;
  margin: 0 auto;
}

.tabs_header {
  margin-bottom: 10px;
  list-style: none;
  padding: 0;
  display: flex;
}

.tabs_header li {
  width: 80px;
  text-align: center;
  padding: 10px 20px;
  margin-right: 10px;
  background-color: #ddd;
  border-radius: 5px;
  cursor: pointer;
  transition: 0.4 all ease-out;
}

.tabs_header li.selected {
  background-color: #0984e3;
  color: white;
}
</style>
