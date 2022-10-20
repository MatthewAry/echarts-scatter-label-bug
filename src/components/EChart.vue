<!-- EChart
  Created by Matthew Ary on 20-10-2022.
  Email: matthew.ary@acquisitionsimplicity.com
         matthewj.c.ary@gmail.com
-->
<template>
  <VCard class="relative" min-height="150">
    <VImg class="plotgraph-colors rounded" :src="PlotgraphColors" />
    <div ref="echart" class="chart" />
  </VCard>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import PlotgraphColors from '@/assets/plotgraph-colors.jpg';
import * as echarts from 'echarts/core';
import { CanvasRenderer } from 'echarts/renderers';
import { ScatterChart } from 'echarts/charts';
import {
  GridComponent,
  MarkLineComponent,
  TooltipComponent,
} from 'echarts/components';
import type { EChartsType } from 'echarts/types/dist/shared'

echarts.use([
  CanvasRenderer,
  ScatterChart,
  TooltipComponent,
  GridComponent,
  MarkLineComponent,
]);

export default defineComponent({
  name: 'EChart',
  setup() {
    return {
      PlotgraphColors,
    };
  },
  data: () => ({
    chart: null as EChartsType | null
  }),
  computed: {
    options() {
      return {
        grid: { bottom: 30, top: 60, left: 140, right: 240 },
        textStyle: {
          fontFamily: "'Outfit', sans-serif",
          fontWeight: 500,
          fontSize: 14,
        },
        tooltip: {
          trigger: 'item',
          appendToBody: true,
          className: 'v-application',
          backgroundColor: '',
          borderColor: '',
          borderRadius: 0,
          borderWidth: 0,
          padding: 0,
          shadowBlur: 0,
          shadowOffsetX: 0,
          shadowOffsetY: 0,
        },
        title: [],
        xAxis: {
          min: -50,
          max: 50,
          minInterval: 100,
          type: 'value',
          axisLabel: {
            show: false,
            inside: true,
            showMinLabel: true,
            showMaxLabel: true,
          },
          axisTick: { show: false },
          splitLine: { show: false },
        },
        yAxis: {
          min: -1,
          max: 1,
          minInterval: 100,
          type: 'value',
          inverse: true,
          axisLabel: { show: false },
          axisTick: { show: false },
          splitLine: { show: false },
        },
        series: [
          {
            type: 'scatter',
            data: [
              {
                name: 'Medical Innovations',
                value: [42.18540110180368, -0.11032169862972985],
                itemStyle: { color: '#a6cee3' },
                tooltip: {
                  formatter: {
                    _custom: {
                      type: 'function',
                      display:
                        '<span style="opacity:.5;">function</span> formatter()',
                      tooltip:
                        '<pre>()=>{const t=document.createElement("div");t.setAttribute("class","d-flex");const r=document.createElement("div");function s(e,t){const r=[],s=document.createElement("div");s.setAttribute("class","text-caption"),s.setAttribute("style","grid-column: 1"),s.appendChild(document.createTextNode(e));const a=document.createElement("div");return a.setAttribute("class","text-body-2 pl-1"),a.setAttribute("style","grid-column: 2"),a.appendChild(document.createTextNode(t)),r.push(s,a),r}r.setAttribute("style",`background-color: ${this.vendorColors[e.id]}; width: 10px; height: 10px;`),r.setAttribute("class","rounded-circle mr-1 mt-2"),t.appendChild(r);const a=document.createElement("div");a.setAttribute("style","display: grid;");const o=document.createElement("div");o.appendChild(document.createTextNode(e.name)),o.setAttribute("class","text-subtitle-1"),o.setAttribute("style","grid-column: 1 / span 2"),a.appendChild(o),[s("Cost:",`$${l(this.value.costs[e.id])}`),s("Performance:",Math.round(10*(this.value.vendorOverallPerformance[e.id]+Number.EPSILON))/10+" pts")].flat().forEach((e=>a.appendChild(e))),t.appendChild(a);const i=document.createElement("div");return i.appendChild(t),i.setAttribute("class","v-card v-sheet v-sheet--outlined py-2 px-3 elevation-3"),i.setAttribute("style","background-color: #ffffff; border: 1px solid #DFE4ED;"),i}</pre>',
                      _reviveId: 356,
                    },
                  },
                  textStyle: { color: '#1D2533' },
                },
              },
              {
                name: 'INTLMED',
                value: [41.89469977108645, 0.20366304466575813],
                itemStyle: { color: '#1f78b4' },
                tooltip: {
                  formatter: {
                    _custom: {
                      type: 'function',
                      display:
                        '<span style="opacity:.5;">function</span> formatter()',
                      tooltip:
                        '<pre>()=>{const t=document.createElement("div");t.setAttribute("class","d-flex");const r=document.createElement("div");function s(e,t){const r=[],s=document.createElement("div");s.setAttribute("class","text-caption"),s.setAttribute("style","grid-column: 1"),s.appendChild(document.createTextNode(e));const a=document.createElement("div");return a.setAttribute("class","text-body-2 pl-1"),a.setAttribute("style","grid-column: 2"),a.appendChild(document.createTextNode(t)),r.push(s,a),r}r.setAttribute("style",`background-color: ${this.vendorColors[e.id]}; width: 10px; height: 10px;`),r.setAttribute("class","rounded-circle mr-1 mt-2"),t.appendChild(r);const a=document.createElement("div");a.setAttribute("style","display: grid;");const o=document.createElement("div");o.appendChild(document.createTextNode(e.name)),o.setAttribute("class","text-subtitle-1"),o.setAttribute("style","grid-column: 1 / span 2"),a.appendChild(o),[s("Cost:",`$${l(this.value.costs[e.id])}`),s("Performance:",Math.round(10*(this.value.vendorOverallPerformance[e.id]+Number.EPSILON))/10+" pts")].flat().forEach((e=>a.appendChild(e))),t.appendChild(a);const i=document.createElement("div");return i.appendChild(t),i.setAttribute("class","v-card v-sheet v-sheet--outlined py-2 px-3 elevation-3"),i.setAttribute("style","background-color: #ffffff; border: 1px solid #DFE4ED;"),i}</pre>',
                      _reviveId: 357,
                    },
                  },
                  textStyle: { color: '#1D2533' },
                },
              },
              {
                name: 'VitalSense',
                value: [42.91575478580235, -0.0933413460360284],
                itemStyle: { color: '#b2df8a' },
                tooltip: {
                  formatter: {
                    _custom: {
                      type: 'function',
                      display:
                        '<span style="opacity:.5;">function</span> formatter()',
                      tooltip:
                        '<pre>()=>{const t=document.createElement("div");t.setAttribute("class","d-flex");const r=document.createElement("div");function s(e,t){const r=[],s=document.createElement("div");s.setAttribute("class","text-caption"),s.setAttribute("style","grid-column: 1"),s.appendChild(document.createTextNode(e));const a=document.createElement("div");return a.setAttribute("class","text-body-2 pl-1"),a.setAttribute("style","grid-column: 2"),a.appendChild(document.createTextNode(t)),r.push(s,a),r}r.setAttribute("style",`background-color: ${this.vendorColors[e.id]}; width: 10px; height: 10px;`),r.setAttribute("class","rounded-circle mr-1 mt-2"),t.appendChild(r);const a=document.createElement("div");a.setAttribute("style","display: grid;");const o=document.createElement("div");o.appendChild(document.createTextNode(e.name)),o.setAttribute("class","text-subtitle-1"),o.setAttribute("style","grid-column: 1 / span 2"),a.appendChild(o),[s("Cost:",`$${l(this.value.costs[e.id])}`),s("Performance:",Math.round(10*(this.value.vendorOverallPerformance[e.id]+Number.EPSILON))/10+" pts")].flat().forEach((e=>a.appendChild(e))),t.appendChild(a);const i=document.createElement("div");return i.appendChild(t),i.setAttribute("class","v-card v-sheet v-sheet--outlined py-2 px-3 elevation-3"),i.setAttribute("style","background-color: #ffffff; border: 1px solid #DFE4ED;"),i}</pre>',
                      _reviveId: 358,
                    },
                  },
                  textStyle: { color: '#1D2533' },
                },
              },
            ],
            symbolSize: 20,
            itemStyle: {
              borderColor: '#ffffff',
              borderWidth: 1.5,
              opacity: 1
            },
            label: {
              show: true,
              formatter: '{b}',
              position: 'right',
              minMargin: 2,
              width: 100,
              overflow: 'break',
              borderWidth: 1,
              borderColor: '#fff',
              padding: [0, 0, 8, 0]
            },
            labelLayout: {
              x: '100%',
              dx: -108,
              y: 60,
              moveOverlap: 'shiftY'
            },
            labelLine: {
              show: true,
              length2: 5,
              lineStyle: {
                color: '#bbb'
              }
            }
          },
          {
            type: 'scatter',
            markLine: {
              label: { show: true },
              symbol: 'none',
              data: [
                {
                  name: 'Low Cost',
                  xAxis: 0,
                  lineStyle: { type: 'solid', color: '#000' },
                  label: {
                    formatter: '{b}',
                    position: 'start',
                    fontSize: 14,
                    fontWeight: 600,
                    color: '#378760',
                  },
                  emphasis: { disabled: true },
                },
                {
                  name: 'High Cost',
                  xAxis: 0,
                  lineStyle: { type: 'solid', color: '#000' },
                  label: {
                    formatter: '{b}',
                    position: 'end',
                    fontSize: 14,
                    fontWeight: 600,
                    color: '#C63629',
                  },
                  emphasis: { disabled: true },
                },
                {
                  name: 'Low Performance',
                  yAxis: 0,
                  lineStyle: { type: 'solid', color: '#000' },
                  label: {
                    formatter: '{b}',
                    position: 'start',
                    fontSize: 14,
                    fontWeight: 600,
                    color: '#C63629',
                  },
                  emphasis: { disabled: true },
                },
                {
                  name: 'High Performance',
                  yAxis: 0,
                  lineStyle: { type: 'solid', color: '#000' },
                  label: {
                    formatter: '{b}',
                    position: 'end',
                    fontSize: 14,
                    fontWeight: 600,
                    color: '#378760',
                  },
                  emphasis: { disabled: true },
                },
              ],
              animation: false,
              tooltip: { show: false },
              silent: true,
            },
          },
        ],
      };
    },
  },
  watch: {
    '$vuetify.breakpoint.width'() {
      this.resize();
    },
  },
  mounted() {
    this.activate();
  },
  beforeDestroy() {
    if (this.chart && !this.chart.isDisposed()) this.chart.dispose()
  },
  methods: {
    activate() {
      if (this.$refs.echart) {
        if (this.chart !== null) this.chart.dispose();
        this.chart = echarts.init(this.$refs.echart as HTMLElement, undefined, {
          renderer: 'canvas',
        });
        this.chart.setOption(this.options);
      }
    },
    resize() {
      if (this.chart !== null && !this.chart?.isDisposed()) this.chart.resize();
    },
  },
});
</script>

<style scoped lang="scss">
.relative {
  position: relative;
}
.chart {
  height: 500px;
}
.plotgraph-colors {
  position: absolute;
  bottom: 30px;
  top: 60px;
  left: 140px;
  right: 240px;
  background-size: 100% 100%;
  opacity: 0.3;
}
</style>
