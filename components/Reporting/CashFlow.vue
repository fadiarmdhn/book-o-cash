<template>
  <div class="row">
    <div class="col-md-12">
      <card card-body-classes="table-full-width">
        <h5 slot="header" class="title">Laporan Keuangan</h5>
        <el-table 
        :data="tableData.filter(data => !search || data.name.toLowerCase().includes(search.toLowerCase()))"
        style="width: 100%">
          <el-table-column
            sortable
            label="Name"
            property="name"
          ></el-table-column>
          <el-table-column
            sortable
            label="Date"
            property="country"
          ></el-table-column>
          <el-table-column
            sortable
            label="Tipe"
            property="city"
          ></el-table-column>
          <el-table-column
            sortable
            align="right"
            header-align="right"
            label="Total"
            property="salary"
          ></el-table-column>
          <el-table-column
            align="right">
            <template slot="header" slot-scope="scope">
              <el-input
                v-model="search"
                align="right"
                size="mini"
                placeholder="Type to search"/>
            </template>
            <template slot-scope="scope">
                 <base-button 
                    class="animation-on-hover"
                    size="sm"
                    type="default"
                    @click="handleDetail(scope.$index, scope.row)">
                <i class="tim-icons icon-notes"></i>Detail</base-button>
            </template>
          </el-table-column>
        </el-table>
      </card>
    </div>
  </div>
</template>
<script>
import { Table, TableColumn } from 'element-ui';

export default {
  components: {
    [Table.name]: Table,
    [TableColumn.name]: TableColumn
  },
  data() {
    return {
      tableData: [
        {
          id: 1,
          name: 'Nasi Putih',
          salary: 'Rp 168.738',
          country: '29-10-2020',
          city: 'Masuk'
        },
        {
          id: 2,
          name: 'Ayam Panggang',
          salary: 'Rp 237.789',
          country: '29-10-2020',
          city: 'Masuk'
        },
        {
          id: 3,
          name: 'Rendang',
          salary: 'Rp 163.142',
          country: '10-10-2020',
          city: 'Masuk'
        },
        {
          id: 4,
          name: 'Gulai Ayam',
          salary: 'Rp 185.735',
          country: '12-10-2020',
          city: 'Masuk'
        },
        {
          id: 5,
          name: 'Gulai Ikan',
          salary: 'Rp 130,542',
          country: '13-10-2020',
          city: 'Masuk'
        }
      ],
      search: '',
    };
  },
  methods: {
      handleDetail(index, row) {
        console.log(index, row);
      },
    }
};
</script>

<style>
.table-transparent {
  background-color: transparent !important;
}
</style>
