<template>
  <!-- Создаём блок и список, где элементами являются элементы сворачивающегося меню -->
  <div class="MenuBlock">
    <ul class="list-unstyled ps-0">
      <li class="mb-1" v-for="(item, index) in array" v-bind:key="item">
        <!-- Передаём параметры данных для рендеринга нашего комонента 
        сворачивающегося меню -->
        <CollapseMenuElement
          :ButtonName="item.button"
          :MenuElements="item.element"
          :IndexOfCollapseController="index"
        />
      </li>
    </ul>
  </div>
</template>

<script>
import CollapseMenuElement from "./CollapseMenuElement.vue";

export default {
  name: "CollapseMenu",
  props: {
    array: {
      type: Array,
      required: true,
    },
  },
  components: {
    //Использующиеся компоненты
    CollapseMenuElement,
  },
};
</script>

<style></style>
