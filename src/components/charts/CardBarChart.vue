<script>
import { Bar } from 'vue-chartjs'

// const datasets = [
//   {
//     label: 'My First dataset',
//     backgroundColor: 'rgba(255,255,255,.3)',
//     borderColor: 'transparent',
//     //data: [78, 81, 80, 45, 34, 12, 40, 75, 34, 89, 32, 68, 54, 72, 18, 98]
//     data: this.data
//   }
// ]

export default Bar.extend({
  props: ['height', 'data', 'barbgcolor', 'barbordercolor'],
  mounted () {
    this.renderChart({
      labels: ['', '', '', '', '', '', '', '', '', '', '', '', '', '', '', ''],
      //datasets: datasets
      datasets: [
                  {
                    label: 'My First dataset',
                    //backgroundColor: 'rgba(255,255,255,.3)',
                    backgroundColor: this.barbgcolor,
                    //borderColor: 'transparent',
                    borderColor: this.barbordercolor,
                    //data: [78, 81, 80, 45, 34, 12, 40, 75, 34, 89, 32, 68, 54, 72, 18, 98]
                    data: this.data
                  }
                ]

    }, {
      maintainAspectRatio: false,
      legend: {
        display: false
      },
      scales: {
        xAxes: [{
          display: false,
          categoryPercentage: 1,
          barPercentage: 0.5
        }],
        yAxes: [{
          display: false
        }]
      }
    })
  }
})
</script>
