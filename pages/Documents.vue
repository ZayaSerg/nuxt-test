<template>
  <div class="">
    <h1>Documents &#10004;</h1>
    <el-main>
      <el-table
        :data="tableData"
        height="500"
        style="width: 100%">
        <el-table-column
          property="status"
          label="Status"
          width="120"/>
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
          label="Description / Notes"/>
      </el-table>
    </el-main>
  </div>
</template>

<script>
export default {
  data() {
    const item = {
      status: '&#10004;',
      document: 'Sale',
      date: '2016-05-03',
      shop: 'TC TSUM',
      ammount: '1287.65',
      client: 'Retail Buyer',
      author: 'Tom',
      description: 'No. 189, Grove St, Los Angeles'
    }
    return {
      tableData: Array(20).fill(item)
    }
  }
}
</script>

<style>
</style>
