<template>
  <MDBNavbar expand="sm" container fixed="top">
    <ul class="hr">
      <li v-for="(page, index) in pages" :key="index" class="page-elem">
        {{ page }}<i v-if="!(page == pages[pages.length - 1])" class="angle fa fa-angle-right" aria-hidden="true"></i>
      </li>
    </ul>

    <MDBNavbarNav right>
      <!-- Dropdown -->
      <MDBDropdown v-model="dropdown3">
        <MDBDropdownToggle
          tag="a"
          class="nav-link"
          @click="dropdown3 = !dropdown3"
          ><i class="fa-solid fa-bell"></i
        ></MDBDropdownToggle>
      </MDBDropdown>
    </MDBNavbarNav>

    <MDBNavbarNav vertical>
      <!-- Dropdown -->
      <MDBDropdown v-model="dropdown2">
        <MDBDropdownToggle
          tag="a"
          class="nav-link"
          @click="dropdown2 = !dropdown2"
          >{{ user }}</MDBDropdownToggle
        >
        <MDBDropdownMenu>
          <MDBDropdownItem href="#">Профиль</MDBDropdownItem>
          <MDBDropdownItem href="#">Настройки</MDBDropdownItem>
          <MDBDropdownItem href="#">Выход</MDBDropdownItem>
        </MDBDropdownMenu>
      </MDBDropdown>
    </MDBNavbarNav>
  </MDBNavbar>
</template>

<script>
import {
  MDBNavbar,
  MDBNavbarNav,
  MDBDropdown,
  MDBDropdownToggle,
  MDBDropdownMenu,
  MDBDropdownItem,
} from "mdb-vue-ui-kit";
import { ref } from "vue";
export default {
  name: "UserBar",
  props: {
    pages: {
      type: Array,
      required: true,
    },
    user: {
      type: String,
      required: true,
    },
  },
  components: {
    MDBNavbar,
    MDBNavbarNav,
    MDBDropdown,
    MDBDropdownToggle,
    MDBDropdownMenu,
    MDBDropdownItem,
  },
  setup() {
    const dropdown2 = ref(false);
    const dropdown3 = ref(false);

    return {
      new_messages: 5,
      updates: 2,
      news: 0,
      dropdown2,
      dropdown3,
    };
  },
};
</script>

<style>
ul,
li {
  margin: 0; /* Обнуляем значение отступов */
  padding: 0;
}
ul.hr li {
  display: inline; /* Отображать как строчный элемент */
}
.angle {
  padding-left: 3px;
  padding-right: 3px;
}
</style>
