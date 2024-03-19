<template>
  <div>
    <el-table :data="tableData" border stripe style="width: 100%">
      <el-table-column type="index" width="40"></el-table-column>
      <el-table-column prop="name" label="商品名称" width="300"></el-table-column>
      <el-table-column prop="price" label="商品单价" width="100"></el-table-column>
      <el-table-column label="购买数量" width="100"></el-table-column>
      <el-table-column label="操作" width="100"></el-table-column>
    </el-table>
    <el-descriptions>
      <el-descriptions-item label="总价">￥{{ totalPrice }}</el-descriptions-item>
    </el-descriptions>
  </div>
</template>

<script>
export default {
  data () {
    return {
      tableData: [
        {
          id: 1,
          name: 'AirPods',
          price: 1288,
          amount: 2
        },
        {
          id: 2,
          name: 'BeatX 入耳式耳机',
          price: 1188,
          amount: 5
        },
        {
          id: 3,
          name: 'Beats Solo3 Wireless 头戴式耳机',
          price: 2288,
          amount: 1
        }
      ],
      totalPrice: 0
    }
  },
  methods () {

  },
  created () {
    for (let i = 0; i < this.tableData.length; ++i) {
      this.totalPrice += this.tableData[i].amount * this.tableData[i].price
    }
  }
}
</script>

<style></style>
