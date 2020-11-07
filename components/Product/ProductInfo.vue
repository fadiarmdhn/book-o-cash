<template>
  <div class="row">
    <div class="col-md-12">
      <card card-body-classes="table-full-width">
        <h3 slot="header" class="title">Product List</h3>
          <div class="text-right">
            <base-button 
              class="animation-on-hover"
              size="sm" 
              type="info">Add Product
            </base-button>
          </div>
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
            label="Category"
            property="category"
          ></el-table-column>

          <el-table-column
            sortable
            align="center"
            header-align="center"
            label="Selling Price"
            property="price"
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
          
          <el-table-column header-align="right">
            <div slot-scope="{row}" class="text-right">
              <el-tooltip content="Details"
                          :open-delay="300"
                          placement="top">
                <base-button type="default" size="sm" icon>
                  <i class="tim-icons icon-notes"></i>
                </base-button>
              </el-tooltip>

              <el-tooltip content="Edit"
                          :open-delay="300"
                          placement="top">
                <base-button type="info" size="sm" icon>
                  <i class="tim-icons icon-pencil"></i>
                </base-button>
              </el-tooltip>

              <el-tooltip content="Delete"
                          :open-delay="300"
                          placement="top">
                <base-button type="danger" size="sm" icon>
                  <i class="tim-icons icon-trash-simple"></i>
                </base-button>
              </el-tooltip>

            </div>
          </el-table-column>
        </el-table>  
      </card>
      <div >
          <base-pagination 
            :page-count="5" 
            v-model="defaultPagination"></base-pagination>
        </div>
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
          price: 'Rp 168.738',
          category: 'Food'
        },
        {
          id: 2,
          product: 'Nasi Liwet',
          price: 'Rp 237.789',
          category: 'Food'
        },
        {
          id: 3,
          product: 'Puyunghai',
          price: 'Rp 163.142',
          category: 'Food'
        },
        {
          id: 4,
          product: 'Gulai Ayam',
          price: 'Rp 185.735',
          category: 'Food'
        },
        {
          id: 5,
          product: 'Kwetiau Goreng',
          price: 'Rp 130,542',
          category: 'Food'
        },
        {
          id: 6,
          product: 'Teh Manis',
          price: 'Rp 130,542',
          category: 'Beverage'
        },
        {
          id: 7,
          product: 'Jus Jeruk',
          price: 'Rp 130,542',
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
