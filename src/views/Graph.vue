<template>
  <div id="container">
    <div className="title">Vue G6</div>
    <div id="mountNode"></div>
  </div>
</template>
<script>
import G6 from '@antv/g6'

export default {
  name: 'minimap',
  data () {
    return {
      graph: null,
      graphData: {
        nodes: [{
          id: 'node1',
          x: 100,
          y: 200
        },
        {
          id: 'node2',
          x: 300,
          y: 200
        }],
        edges: [{
          target: 'node2',
          source: 'node1'
        }]
      }
    }
  },
  mounted () {
    this.graph = new G6.Graph({
      container: 'mountNode',
      width: 500,
      height: 500
    })
    this.graph.read(this.graphData)
  }
}
</script>
