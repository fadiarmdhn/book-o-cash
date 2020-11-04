<template>
  <div class="row">
    <div class="col-md-12">
      <card card-body-classes="table-full-width">
        <h3 slot="header" class="title">Sales Record</h3>
        <base-button 
          class="animation-on-hover" 
          size="sm" 
          type="info">Add Order</base-button>
        <el-table 
        :data="tableData.filter(data => !search || data.name.toLowerCase().includes(search.toLowerCase()))"
        style="width: 100%">
          <el-table-column
            sortable
            label="Order ID"
            property="orderId"
          ></el-table-column>
          <el-table-column
            sortable
            label="Name"
            property="name"
          ></el-table-column>
          <el-table-column
            sortable
            label="Order Type"
            property="type"
          ></el-table-column>
          <el-table-column
            sortable
            align="center"
            header-align="center"
            label="Table Number"
            property="tableNumber"
          ></el-table-column>
          <el-table-column
            sortable
            align="center"
            header-align="center"
            label="Cashier"
            property="cashier"
          ></el-table-column>
          <el-table-column
            sortable
            align="center"
            header-align="center"
            label="Status"
            property="status"
          ></el-table-column>
          <el-table-column>
            <div slot-scope="scope">
                 <base-button 
                    size="sm"
                    type="warning"
                    @click="handleDetail(scope.$index, scope.row)"
                  > Edit</base-button>
            </div>
          </el-table-column>
          <el-table-column>
            <div slot-scope="scope">
                 <base-button 
                    size="sm"
                    type="success"
                    @click="handleDetail(scope.$index, scope.row)"
                  > Finish</base-button>
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
          orderId: '#0001',
          tableNumber: '08',
          name: 'Aan',
          type: 'Dine-in',
          cashier: 'Bambang',
          status: 'In process'
        },
        {
          id: 2,
          orderId: '#0002',
          tableNumber: '03',
          name: 'Ahmad',
          type: 'Dine-in',
          cashier: 'Bambang',
          status: 'In process'
        },
        {
          id: 3,
          orderId: '#0003',
          tableNumber: '42',
          name: 'Bob',
          type: 'Dine-in',
          cashier: 'Bambang',
          status: 'In process'
        },
        {
          id: 4,
          orderId: '#0004',
          tableNumber: '-',
          name: 'Yuwono',
          type: 'Takeaway',
          cashier: 'Bambang',
          status: 'In process'
        },
        {
          id: 5,
          orderId: '#0005',
          tableNumber: '-',
          name: 'Fadia',
          type: 'Takeaway',
          cashier: 'Bambang',
          status: 'In process'
        },
        {
          id: 6,
          orderId: '#0006',
          tableNumber: '17',
          name: 'Indah',
          type: 'Dine-in',
          cashier: 'Bambang',
          status: 'In process'
        },
        {
          id: 7,
          orderId: '#0007',
          tableNumber: '-',
          name: 'Puspita',
          type: 'Takeaway',
          cashier: 'Bambang',
          status: 'In process'
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
