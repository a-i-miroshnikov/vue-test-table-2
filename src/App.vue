<template>
  <div class="container-fluid">
    <div class="row">
      <div
        class="col-lg-2 col-md-2 col-sm-2 col-xs-3 flex-shrink-0 p-3 bg-white"
      >
        <a
          href="#"
          class="d-flex align-items-center justify-content-start pb-3 mb-3 link-dark text-decoration-none border-bottom"
        >
          <span class="fs-5 fw-semibold">Учёт объектов энергетики</span>
        </a>
        <div id="nav"><CollapseMenu :array="array" /></div>
      </div>
      <div class="col-lg-10 col-md-10 col-sm-10 col-xs-9">
        <div class="short-div">
          <UserBar :user="user" :pages="pages"></UserBar>
        </div>
        <div class="short-div">
          <div id="table-example">
            <TableData :columns="columns" :entries="entries" />
          </div>
        </div>
      </div>
    </div>
    <router-view />
  </div>
</template>

<script>
import CollapseMenu from "./components/CollapseMenu.vue";
import TableData from "./components/TableBase.vue";
import UserBar from "./components/UserBar.vue";

export default {
  name: "App",
  components: {
    //Использующиеся компоненты
    CollapseMenu,
    TableData,
    UserBar,
  },
  data() {
    return {
      array: [
        {
          button: "Теплоэнергетика",
          element: [
            "Котельные",
            "Потребители",
            "Котлы",
            "Насосы котельной",
            "Теплообменное оборудование котельной",
            "Дымовые трубы",
            "Объемы отпуска тепловой энергии",
            "Затраты на котельную",
            "Затраты на тепловую сеть",
            "Ремонты котельной",
            "Аварии на котельной",
            "Участки тепловой сети",
            "Аварии на теплосети",
            "Ремонты теплосети",
            "Тепловые камеры",
            "ЦТП / Насосные",
            "Насосы ЦТП / Насосной",
            "Теплообменники ЦТП / Насосной",
            "Аварии в ЦТП / Насосной",
            "Ремонты ЦТП / Насосной",
            "Затраты на ЦТП / Насосную",
          ],
        },
        {
          button: "Электроэнергетика",
          element: [
            "Потребители",
          ],
        },
        {
          button: "Газоснабжение",
          element: [
            "Потребители",
          ],
        },
      ],
      columns: [
        { name: "id", text: "ID" },
        { name: "name", text: "Наименование" },
        { name: "position", text: "Муниципальное образование" },
        { name: "salary", text: "Адрес" },
      ],
      entries: [
        { id: "1", name: "Котельная на Московской", position: "Липецк", salary: "99" },
        { id: "2", name: "Котельная на Космонавтов", position: "Липецк", salary: "95" },
        { id: "3", name: "Котельная на Гагарина", position: "Липецк", salary: "93" },
        { id: "4", name: "Котельная на Московской", position: "Липецк", salary: "99" },
        { id: "5", name: "Котельная на Космонавтов", position: "Липецк", salary: "95" },
        { id: "6", name: "Котельная на Гагарина", position: "Липецк", salary: "93" },
        { id: "7", name: "Котельная на Московской", position: "Липецк", salary: "99" },
        { id: "8", name: "Котельная на Космонавтов", position: "Липецк", salary: "95" },
        { id: "9", name: "Котельная на Гагарина", position: "Липецк", salary: "93" },
        { id: "10", name: "Котельная на Московской", position: "Липецк", salary: "99" },
        { id: "11", name: "Котельная на Космонавтов", position: "Липецк", salary: "95" },
        { id: "12", name: "Котельная на Гагарина", position: "Липецк", salary: "93" },
        { id: "13", name: "Котельная на Московской", position: "Липецк", salary: "99" },
        { id: "14", name: "Котельная на Космонавтов", position: "Липецк", salary: "95" },
        { id: "15", name: "Котельная на Гагарина", position: "Липецк", salary: "93" },
        { id: "16", name: "Котельная на Московской", position: "Липецк", salary: "99" },
        { id: "17", name: "Котельная на Космонавтов", position: "Липецк", salary: "95" },
        { id: "18", name: "Котельная на Гагарина", position: "Липецк", salary: "93" },
        { id: "19", name: "Котельная на Московской", position: "Липецк", salary: "99" },
        { id: "20", name: "Котельная на Космонавтов", position: "Липецк", salary: "95" },
        { id: "21", name: "Котельная на Гагарина", position: "Липецк", salary: "93" },
        { id: "22", name: "Котельная на Московской", position: "Липецк", salary: "99" },
        { id: "23", name: "Котельная на Космонавтов", position: "Липецк", salary: "95" },
        { id: "24", name: "Котельная на Гагарина", position: "Липецк", salary: "93" },
      ],
      pages: ["Теплоэнергетика", "Котельные"],
      user: "Admin Admin",
    };
  },
};
</script>

<style>
.container-fluid {
  padding-left: 0px !important;
}
#table-example {
  margin-top: 3px !important;
}
</style>
