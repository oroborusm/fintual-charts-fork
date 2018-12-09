<template>
  <div id="app">
    <nav class="navbar navbar-expand-lg navbar-light">
      <div class="container">
        <a class="navbar-brand" href="https://fintual.com" target="_blank">
          <img alt="fintual" class="navbar-brand" src="img/logo.png">
        </a>
      </div>
    </nav>

    <div class="container">
      <Chart v-for="(fund, index) in funds" :key="`fund-chart-${index}`" :real-asset-id="fund.realAssetId" :name="fund.name" />
    </div>
  </div>
</template>

<script>
import Chart from './components/Chart.vue'
export default {
  name: 'app',
  components: {
    Chart
  },
  data: function () {
    return {
      funds: [
        {
          realAssetId: 186,
          name: "Risky Norris",
        },
        {
          realAssetId: 187,
          name: "Moderate Pitt",
        },
        {
          realAssetId: 188,
          name: "Conservative Clooney",
        },
      ]
    };
  }
}
</script>

<style lang="sass">
#app
  font-family: 'Open Sans', sans-serif !important
  text-align: center
  color: #2c3e50
.navbar
  background-color: white
  margin-bottom: 32px
  .navbar-brand
    max-width: 150px

.chart
  margin-bottom: 32px
  .highcharts-container
    .highcharts-root
      width: 100%
      .highcharts-range-selector-group
        .highcharts-range-selector-buttons
          text
            fill: #dae0e5 !important
          .highcharts-button
            .highcharts-button-box
              border-radius: 50%
              color: #3DADE2
              cursor: pointer
              height: 32px
              rx: 20px
              ry: 20px
              stroke: #3DADE2
              width: 32px
            text
              color: #3DADE2 !important
              fill: #3DADE2 !important
              transform: translateY(6px)
          .highcharts-button-disabled
            .highcharts-button-box
              color: #dae0e5
              stroke: #dae0e5
            text
              color: #dae0e5
              cursor: default !important
              stroke: #dae0e5
          .highcharts-button-pressed
            .highcharts-button-box
              fill: #3DADE2
              stroke: #3DADE2
            text
              color: white !important
              cursor: default !important
              fill: white !important
      
        text
          transform: translateY(6px)
      .highcharts-input-group
        .highcharts-label
          .highcharts-label-box
            height: 32px
            rx: 5px
            ry: 5px
            stroke: #4D4D4D
            stroke-width: 2
          text
            fill: #dae0e5 !important
            transform: translateY(6px)
            tspan
              fill: #4D4D4D
      .highcharts-title
        display: block
        fill: none
        text-align: left
        tspan
          font-family: 'Lato'
          font-weight: 900


.highcharts-graph
  stroke: #3DADE2
  stroke-width: 3
.highcharts-markers
  .highcharts-halo
    fill: #333

.highcharts-tooltip-box
  .highcharts-label-box
    stroke: #dae0e5
    stroke-width: 2 !important
  text
    tspan
      fill: #333
.highcharts-navigator-handle
  rx: 5px
  ry: 5px
  stroke: #333
.highcharts-navigator-mask-inside
  fill: rgba(48,96,139,.2)
@media (max-width: 768px)
  nav
    .container
      justify-content: center !important
      .navbar-brand
        margin: 0
  .highcharts-input-group
    transform: translate(8px, 50px) !important
</style>
