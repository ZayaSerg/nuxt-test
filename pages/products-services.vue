<template>
  <div class="">
    <h1>Products & Services</h1>
    <div style="margin-top: 20px">
      <el-button @click="toggleSelection([tableData3[1], tableData3[2]])">Toggle selection status of second and third rows</el-button>
      <el-button @click="toggleSelection()">Clear selection</el-button>
    </div>
    <el-table
      ref="multipleTable"
      :data="tableData3"
      style="width: 100%"
      @selection-change="handleSelectionChange">
      <el-table-column
        type="selection"
        width="55"/>
      <el-table-column
        property="document"
        label="Document"
        width="120"/>
      <el-table-column
        property="date"
        label="Date"
        width="120"/>
      <el-table-column
        property="shop"
        label="Shop"
        width="120"/>
      <el-table-column
        property="ammount"
        label="Ammount"
        width="120"/>
      <el-table-column
        property="client"
        label="Client"
        width="120"/>
      <el-table-column
        property="author"
        label="Author"
        width="120"/>
      <el-table-column
        property="description"
        label="Description / Notes"
        show-overflow-tooltip/>
    </el-table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tableData3: [
        {
          document: 'Sale',
          date: '2016-05-03',
          shop: 'TC TSUM',
          ammount: '1287.65',
          client: 'Retail Buyer',
          author: 'Tom',
          description: 'No. 189, Grove St, Los Angeles'
        },
        {
          document: 'Sale',
          date: '2016-05-03',
          shop: 'TC TSUM',
          ammount: '1287.65',
          client: 'Retail Buyer',
          author: 'Tom',
          description: 'No. 189, Grove St, Los Angeles'
        },
        {
          document: 'Sale',
          date: '2016-05-03',
          shop: 'TC TSUM',
          ammount: '1287.65',
          client: 'Retail Buyer',
          author: 'Tom',
          description: 'No. 189, Grove St, Los Angeles'
        },
        {
          document: 'Sale',
          date: '2016-05-03',
          shop: 'TC TSUM',
          ammount: '1287.65',
          client: 'Retail Buyer',
          author: 'Tom',
          description: 'No. 189, Grove St, Los Angeles'
        },
        {
          document: 'Sale',
          date: '2016-05-03',
          shop: 'TC TSUM',
          ammount: '1287.65',
          client: 'Retail Buyer',
          author: 'Tom',
          description: 'No. 189, Grove St, Los Angeles'
        },
        {
          document: 'Sale',
          date: '2016-05-03',
          shop: 'TC TSUM',
          ammount: '1287.65',
          client: 'Retail Buyer',
          author: 'Tom',
          description: 'No. 189, Grove St, Los Angeles'
        },
        {
          document: 'Sale',
          date: '2016-05-03',
          shop: 'TC TSUM',
          ammount: '1287.65',
          client: 'Retail Buyer',
          author: 'Tom',
          description: 'No. 189, Grove St, Los Angeles'
        },
        {
          document: 'Sale',
          date: '2016-05-03',
          shop: 'TC TSUM',
          ammount: '1287.65',
          client: 'Retail Buyer',
          author: 'Tom',
          description: 'No. 189, Grove St, Los Angeles'
        },
        {
          document: 'Sale',
          date: '2016-05-03',
          shop: 'TC TSUM',
          ammount: '1287.65',
          client: 'Retail Buyer',
          author: 'Tom',
          description: 'No. 189, Grove St, Los Angeles'
        },
        {
          document: 'Sale',
          date: '2016-05-03',
          shop: 'TC TSUM',
          ammount: '1287.65',
          client: 'Retail Buyer',
          author: 'Tom',
          description: 'No. 189, Grove St, Los Angeles'
        }
      ],
      multipleSelection: []
    }
  },

  methods: {
    toggleSelection(rows) {
      if (rows) {
        rows.forEach(row => {
          this.$refs.multipleTable.toggleRowSelection(row)
        })
      } else {
        this.$refs.multipleTable.clearSelection()
      }
    },
    handleSelectionChange(val) {
      this.multipleSelection = val
    }
  }
}
</script>
