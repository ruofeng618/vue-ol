<template>
    <div id="map" ref="rootmap">
    </div>
</template>
<script>
import 'ol/ol.css'
import Map from 'ol/Map'
import View from 'ol/View'
import TileLayer from 'ol/layer/Tile'
import OSM from 'ol/source/OSM'
export default {
  data () {
    return {
      map: null
    }
  },
  mounted () {
    this.map = new Map({
      target: 'map',
      layers: [
        new TileLayer({
          source: new OSM()
        })
      ],
      view: new View({
        projection: 'EPSG:4326', // 使用这个坐标系
        center: [114.064839, 22.548857], // 深圳
        zoom: 12
      })
    })
  }
}
</script>
<style>
#map{height:100%;}
/*隐藏ol的一些自带元素*/
</style>
