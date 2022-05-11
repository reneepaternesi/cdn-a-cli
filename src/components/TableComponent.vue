<template>
  <div>
    <table class="table table-striped table-bordered table-hover">
      <thead class="thead-dark">
        <tr>
          <th v-for="(title, i) in titles" :key="i" scope="col">{{ title }}</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(entry, i) in entries" :key="i">
          <td>{{entry.id}}</td>
          <td>{{entry.name}}</td>
          <td>{{entry.cantidad}}</td>
          <td>
            <img :src="entry.imag" width="60" height="60"/>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
     name: 'TableComponent',
     props: {
        titles: {
            type: Array,
            required: true
        },
        entries: {
            type: Array,
            required: true
        },
        stylesObject: {
            type: Object,
            required: false
        },
        defaultStyles: Boolean
     }

}
</script>

<style scoped>
    .table {
        color: #212529;
        background-color: gray;
    }

    .table .thead-dark th {
        background-color: gray;
        border-color: #212529;
    }

    .sienna-font .table{
        color: sienna;
    }

    .crimson-font .table{
        color: crimson;
    }

    .blue-font .table{
        color: #09009f;
    }

    .burly-mode .table{
        background-color: burlywood;
    }

    /* table styles */
    .burly-mode .table .thead-dark th {
        background-color: sienna;
        border-color: burlywood;
    }

    .light-mode .table{
        background-color: lightpink;
    }

    .light-mode .table .thead-dark th {
        background-color: crimson;
        border-color: lightpink;
    }

    .blue-mode .table{
        background-color: lightskyblue;
    }

    .blue-mode .table .thead-dark th {
        background-color: #09009f;
        border-color: lightskyblue;
    }
</style>