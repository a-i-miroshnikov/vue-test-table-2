<template>
  <table
    id="table"
    style="width: 100%"
    class="table table-bordered table-striped"
  >
    <thead>
      <tr>
        <th v-for="th in TableHeader" :key="th">
          <i class="fa fa-search" aria-hidden="true"></i>
        </th>
      </tr>
      <tr>
        <th v-for="th in TableHeader" :key="th">
          {{ th.text }}
        </th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="td in TableData" :key="td">
        <td>{{ td.id }}</td>
        <td>{{ td.name }}</td>
        <td>{{ td.position }}</td>
        <td>{{ td.salary }}</td>
      </tr>
    </tbody>
    <tfoot>
      <tr>
        <th v-for="th in TableHeader" :key="th">
          {{ th.text }}
        </th>
      </tr>
    </tfoot>
  </table>
</template>

<script>
import $ from "jquery";

$(document).ready(function () {
  $("#table tfoot th").each(function () {
    var title = $(this).text();
    $(this).html(
      '<input type="text" style="width: 100%;" placeholder="Поиск по \'' +
        title +
        "'\" />"
    );
  });

  $("#table").DataTable({
    initComplete: function () {
      // Apply the search
      this.api()
        .columns()
        .every(function () {
          var that = this;
          $("input", this.footer()).on("keyup change clear", function () {
            if (that.search() !== this.value) {
              that.search(this.value).draw();
            }
          });
        });
    },
    language: {
      infoFiltered: "(Отфильтровано из _MAX_ записей)",
      search: "Поиск:",
      lengthMenu: "Показать _MENU_ записей на странице",
      zeroRecords: "Ничего не найдено",
      info: "Страница _PAGE_ из _PAGES_",
      infoEmpty: "Ничего не найдено",
      paginate: {
        previous: "Назад",
        next: "Далее",
      },
    },
    scrollY: 200,
    scrollX: true,
    lengthMenu: [
      [5, 10, 15, -1],
      [5, 10, 15, "Все"],
    ],
  });
});

export default {
  name: "TableBase",
  props: {
    columns: Array,
    entries: Array,
  },
  computed: {
    TableHeader() {
      return this.columns || [];
    },
    TableData() {
      return this.entries || [];
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
