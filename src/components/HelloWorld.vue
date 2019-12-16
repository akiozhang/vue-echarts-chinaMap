<template>
  <div class="hello">
    <div id="myChart" class="chartInit" ref="chart"></div>
    <!-- <ul>
      <li v-for="(item, index) in lodashData" :key="index">
        {{item}}
      </li>
      <div>{{differentNum}}</div>
    </ul> -->
  </div>
</template>

<script>
  // import _ from 'lodash'
//  const zhongguo = require('echarts/map/js/china');
//  import Jquery from 'jquery'
//  import echarts from 'echarts'
 import {makeChart, areaProjects} from '../utils'
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() { 
    return {
      lodashData: [],
      differentNum: null
    }
  },
  mounted() {
    // Jquery.ajax(zhongguo, function(geoJson) {
    // echarts.registerMap('china', geoJson);
    this.drawChart()
// })
  },
  methods: {
    drawChart() {
      var bar_dv = this.$refs.chart;
      if(bar_dv) {
       makeChart('myChart', {
        bgColor: '#154e90', // 画布背景色
        mapName: 'china', // 地图名
        text: 'by:wxw',
        goDown: true, // 是否下钻           	
        data : areaProjects
    });
      }

    }
    // _getlodashData() {
      // this.lodashData = _.differenceBy([2.5, 1.6, 1.3, 1.5], [4.4, 1], Math.floor)
      // this.differentNum = _.difference([{ 'x': 1, 'y': 2 },{ 'x': 2, 'y': 2 }], [{'x': 1, 'y': 2},{}])
    // }
  }
}
</script>

<style scoped>
.chartInit{
  width: 100%;
  height: 500px;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
