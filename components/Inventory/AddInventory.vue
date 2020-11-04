<template>
  <div class="row">
    <div class="col-md-12">
      <card card-body-classes="table-full-width">
        <h3 slot="header" class="title">Inventory</h3>
        <base-button 
          class="animation-on-hover" 
          size="sm" 
          type="info">Add Stock</base-button>
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
            label="Amount"
            property="amount"
          ></el-table-column>
          <el-table-column
            sortable
            label="Last Update"
            property="update"
          ></el-table-column>
          <el-table-column
            align="center"
            header-align="center"
            label="Alert"
            property="alert"
          ></el-table-column>
          <el-table-column
            align="center"
            header-align="center"
            label="Details">
            <div slot-scope="scope">
                 <base-button 
                    class="animation-on-hover"
                    size="sm"
                    type="default"
                    @click="handleDetail(scope.$index, scope.row)"
                  > Update</base-button>
            </div>
          </el-table-column>
        </el-table>  
        <div >
          <base-pagination 
            :page-count="5" 
            v-model="defaultPagination"></base-pagination>
        </div>
      </card>
    </div>
  </div>
</template>
<script>
import { Table, TableColumn } from 'element-ui';
import {BasePagination} from '@/components'

export default {
  components: {
    [Table.name]: Table,
    [TableColumn.name]: TableColumn,
    BasePagination
  },
  data() {
    return {
      defaultPagination: 1,
      tableData: [
        {
          id: 1,
          name: 'Beras',
          alert: '-',
          amount: '20(kg)',
          update: '29-10-2020'
        },
        {
          id: 2,
          name: 'Telur',
          alert: '-',
          amount: '20(kg)',
          update: '29-10-2020'
        },
        {
          id: 3,
          name: 'Garam',
          alert: '-',
          amount: '2(kg)',
          update: '10-10-2020'
        },
        {
          id: 4,
          name: 'Bawang Putih',
          alert: '-',
          amount: '100(gr)',
          update: '12-10-2020'
        },
        {
          id: 5,
          name: 'Bawang Merah',
          alert: '-',
          amount: '20(kg)',
          update: '13-10-2020'
        },
        {
          id: 6,
          name: 'Cabe Merah',
          alert: '-',
          amount: '10(kg)',
          update: '13-10-2020'
        },
        {
          id: 7,
          name: 'Lada',
          alert: '-',
          amount: '500(gr)',
          update: '13-10-2020'
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
