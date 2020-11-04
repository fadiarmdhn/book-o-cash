<template>
  <div class="row">
    <div class="col-md-12">
      <card card-body-classes="table-full-width">
        <h3 slot="header" class="title">Product List</h3>
        <base-button 
          class="animation-on-hover" 
          size="sm" 
          type="info">Add Product</base-button>
        <el-table 
        :data="tableData.filter(data => !search || data.name.toLowerCase().includes(search.toLowerCase()))"
        style="width: 100%">
          <el-table-column
            sortable
            label="Product"
            property="product"
          ></el-table-column>
          <el-table-column
            sortable
            label="Date"
            property="date"
          ></el-table-column>
          <el-table-column
            sortable
            label="Category"
            property="category"
          ></el-table-column>
          <el-table-column
            sortable
            align="center"
            header-align="center"
            label="Purchase Price"
            property="purchase"
          ></el-table-column>
          <el-table-column
            align="center"
            header-align="center"
            label="Status">
            <div slot-scope="scope">
                 <base-button 
                    size="sm"
                    type="success"
                    @click="handleDetail(scope.$index, scope.row)"
                  > Available</base-button>
            </div>
          </el-table-column>
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
                  > Ingridients</base-button>
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
          product: 'Nasi Goreng',
          purchase: 'Rp 168.738',
          date: '29-10-2020',
          category: 'Food'
        },
        {
          id: 2,
          product: 'Nasi Liwet',
          purchase: 'Rp 237.789',
          date: '29-10-2020',
          category: 'Food'
        },
        {
          id: 3,
          product: 'Puyunghai',
          purchase: 'Rp 163.142',
          date: '10-10-2020',
          category: 'Food'
        },
        {
          id: 4,
          product: 'Gulai Ayam',
          purchase: 'Rp 185.735',
          date: '12-10-2020',
          category: 'Food'
        },
        {
          id: 5,
          product: 'Kwetiau Goreng',
          purchase: 'Rp 130,542',
          date: '13-10-2020',
          category: 'Food'
        },
        {
          id: 6,
          product: 'Teh Manis',
          purchase: 'Rp 130,542',
          date: '13-10-2020',
          category: 'Beverage'
        },
        {
          id: 7,
          product: 'Jus Jeruk',
          purchase: 'Rp 130,542',
          date: '13-10-2020',
          category: 'Beverage'
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
