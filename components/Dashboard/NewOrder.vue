<template>
    <div class="row">
        <div class="col-12">
        <card card-body-classes="table-full-width">
            <h4 slot="header" class="card-title">Orderan Terbaru</h4>
            <el-table :data="tableData">
            <el-table-column
                min-width="150"
                sortable
                label="Name"
                property="name"
            ></el-table-column>
            <el-table-column
                min-width="150"
                sortable
                label="Country"
                property="country"
            ></el-table-column>
            <el-table-column
                min-width="150"
                sortable
                label="City"
                property="city"
            ></el-table-column>
            <el-table-column
                min-width="150"
                sortable
                align="right"
                header-align="right"
                label="Salary"
                property="salary"
            ></el-table-column>
            </el-table>
        </card>
        </div>
    </div>
</template>

<script>
import LineChart from '@/components/Charts/LineChart';
import BarChart from '@/components/Charts/BarChart';
import * as chartConfigs from '@/components/Charts/config';
import TaskList from '@/components/Dashboard/TaskList';
import config from '@/config';
import { Table, TableColumn } from 'element-ui';

export default {
  components: {
    LineChart,
    BarChart,
    TaskList,
    [Table.name]: Table,
    [TableColumn.name]: TableColumn
  },
  data () {
    return {
      tableData: [
        {
          id: 1,
          name: 'Nasi Padang',
          salary: 'Rp10.000',
          country: 'Niger',
          city: 'Oud-Turnhout'
        },
        {
          id: 2,
          name: 'Ayam Rendang',
          salary: 'Rp7.000',
          country: 'Curaçao',
          city: 'Sinaai-Waas'
        },
        {
          id: 3,
          name: 'Gulai Ikan',
          salary: 'Rp5.000',
          country: 'Netherlands',
          city: 'Baileux'
        },
        {
          id: 4,
          name: 'Soap Iga',
          salary: 'Rp20.000',
          country: 'Korea, South',
          city: 'Overland Park'
        },
        {
          id: 5,
          name: 'Dendeng Balado',
          salary: 'Rp10.000',
          country: 'Malawi',
          city: 'Feldkirchen in Kärnten'
        }
      ],
    };
  },
}
</script>