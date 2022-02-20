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
          <span class="fs-5 fw-semibold">Кадровая Система</span>
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
          button: "Сотрудники",
          element: [
            "Штатное расписание",
            "Списочная численность",
            "Список уволенных",
          ],
        },
        {
          button: "Аналитика",
          element: [
            "Прогноз текучести",
            "Прогноз потребности",
            "Интервенции излишков",
          ],
        },
        {
          button: "Справочники",
          element: [
            "Структура предприятия",
            "Причины увольнения",
            "Пенсионные основания",
          ],
        },
      ],
      columns: [
        { name: "id", text: "ID" },
        { name: "name", text: "Name" },
        { name: "position", text: "Position" },
        { name: "salary", text: "Salary" },
      ],
      entries: [
        { id: "1", name: "Bogomolov", position: "student", salary: "99" },
        { id: "2", name: "Sergeev", position: "student", salary: "95" },
        { id: "3", name: "Grishagin", position: "student", salary: "93" },
        { id: "4", name: "Bogomolov", position: "student", salary: "99" },
        { id: "5", name: "Sergeev", position: "student", salary: "95" },
        { id: "6", name: "Grishagin", position: "student", salary: "93" },
        { id: "7", name: "Bogomolov", position: "student", salary: "99" },
        { id: "8", name: "Sergeev", position: "student", salary: "95" },
        { id: "9", name: "Grishagin", position: "student", salary: "93" },
        { id: "10", name: "Bogomolov", position: "student", salary: "99" },
        { id: "11", name: "Sergeev", position: "student", salary: "95" },
        { id: "12", name: "Grishagin", position: "student", salary: "93" },
        { id: "13", name: "Bogomolov", position: "student", salary: "99" },
        { id: "14", name: "Sergeev", position: "student", salary: "95" },
        { id: "15", name: "Grishagin", position: "student", salary: "93" },
        { id: "16", name: "Bogomolov", position: "student", salary: "99" },
        { id: "17", name: "Sergeev", position: "student", salary: "95" },
        { id: "18", name: "Grishagin", position: "student", salary: "93" },
        { id: "19", name: "Bogomolov", position: "student", salary: "99" },
        { id: "20", name: "Sergeev", position: "student", salary: "95" },
        { id: "21", name: "Grishagin", position: "student", salary: "93" },
        { id: "22", name: "Bogomolov", position: "student", salary: "99" },
        { id: "23", name: "Sergeev", position: "student", salary: "95" },
        { id: "24", name: "Grishagin", position: "student", salary: "93" },
      ],
      pages: ["Сотрудники", "Штатное расписание"],
      user: "Vasya Pupkin",
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
