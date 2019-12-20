<template>
  <div class="about">
    <h1>О сервере</h1>
    <div class="diagram"></div>
    <button @click="d3Diagram">Построить</button>
  </div>
</template>

<script>
  import * as d3 from "d3";

  export default {
    name: 'about',
    data: function () {
      return {
        serverFiles: [
          {
            name: 'clear',
            value: 1024
          },
          {
            name: 'busy',
            value: 1024,
            subFiles: [
              {
                name: 'raStudio',
                value: 512,
                subFiles: [
                  {
                    name: 'raDev',
                    value: 256
                  },
                  {
                    name: 'raDist',
                    value: 256
                  }
                ]
              },
              {
                name: 'kvs',
                value: 512
              }
            ]
          }
        ]
      }
    },
    methods: {
      d3Diagram: function($event) {
        let thisData = this.serverFiles;
        let fullSize = null;
        for (let count = 0; count < thisData.length; count++){
          if(thisData[count].name === 'clear' || thisData[count].name === 'busy'){
            fullSize += thisData[count].value;
          }
        }
        d3
          .select('body')
          .select('div.diagram')
          .append('div')
          .classed('chart_area', true)
          .selectAll('div')
          .data(this.serverFiles)
          .enter()
          .append('div')
          .classed('bar_area1', true)
          .classed('bar_area', true)
          .append('div')
          .classed('bar_area1__item', true)
          .classed('bar_area__item', true)
          .style('background-color', 'hsl(240,50%,75%)')
          .style('margin', '2px 0px')
          // eslint-disable-next-line no-console
          .style('width', function (d) {return (d.value / fullSize * 100) / 2 + '%'})
          .text(function (d) {return d.name + ' — ' + d.value})

          .select(function() { return this.parentNode; })
          .data(this.serverFiles[2])
          .style('background-color', 'red')
          .append('div')
          .classed('bar_area2__item', true)
          .classed('bar_area__item', true)
          .style('background-color', 'hsl(240,50%,75%)')
          .style('margin', '2px 0px')
          // eslint-disable-next-line no-console
          .style('width', function (d) {return (d.value / fullSize * 100) / 2 + '%'})
          .text(function (d) {return d.name + ' — ' + d.value})
        ;
        $event.target.remove();
      }
    }
  }
</script>


<style lang="scss" scoped>
  *{
    box-sizing: border-box;
  }
  .about{
    padding: 0 20px;
    h1{
      margin-top: 50px;
      margin-bottom: 30px;
    }
    flex: 1;
    .diagram{
      border-radius: 10px;
      padding: 30px;
      width: 100%;
      height: 600px;
      display: flex;
      border: 1px solid #e4e4e4;
    }
    .bar_area__item{
      height: 100%;
    }
  }
</style>