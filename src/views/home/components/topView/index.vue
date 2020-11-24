<template>
  <div class="topView">
    <el-row :gutter="20">
      <el-col :span="6">
        <el-card shadow="hover">
          <total-sales />
        </el-card>
      </el-col>
      <el-col :span="6">
        <el-card shadow="hover">
          <total-orders />
        </el-card>
      </el-col>
      <el-col :span="6">
        <el-card shadow="hover">
          <today-users />
        </el-card>
      </el-col>
      <el-col :span="6">
        <el-card shadow="hover">
          <total-users />
        </el-card>
      </el-col>
    </el-row>
  </div>
</template>

<script>
// import commonCard from '@/components/commonCard'
import totalSales from '../totalSales'
import totalOrders from '../totalOrders'
import todayUsers from '../todayUsers'
import totalUsers from '../totalUsers'

export default {
  components: {
    // commonCard
    totalSales,
    totalOrders,
    todayUsers,
    totalUsers
  },
  data() {
    return {}
  }
}
</script>

<style>
</style>
