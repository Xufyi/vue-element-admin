<template>
  <div class="home">
    <top-view />
    <sale-view />
    <bottom-view />
    <map-view />
  </div>
</template>

<script>
import topView from './components/topView'
import saleView from './components/saleView'
import bottomView from './components/bottomView'
import mapView from './components/mapView'
import { wordCloud, screenData, mapScatter } from '@/api/home'

export default {
  name: 'Home',
  components: {
    topView,
    saleView,
    bottomView,
    mapView
  },
  data() {
    return {
      reportData: null,
      screenData: null,
      mapScatter: null
    }
  },
  provide() {
    return {
      getReportData: this.getReportData,
      getScreenData: this.getScreenData,
      getMapScatter: this.getMapScatter
    }
  },
  mounted() {
    // 没有服务器，用成了前端mock数据代替
    wordCloud().then(res => {
      this.reportData = res
    })
    screenData().then(res => {
      this.screenData = res
    })
    mapScatter().then(res => (this.mapScatter = res))
  },
  methods: {
    getReportData() {
      return this.reportData
    },
    getScreenData() {
      return this.screenData
    },
    getMapScatter() {
      return this.mapScatter
    }
  }
}
</script>

<style>
.home {
  background: #eee;
  box-sizing: border-box;
  padding: 20px;
}
</style>
