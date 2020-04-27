<template>
  <div class>
    <cardBar
      v-for="stat in Object.values(stats).filter((stat) => stat.type == 'bar')"
      v-bind:data="stat.data"
      v-bind:options="stat.options"
      v-bind:key="stat.id"
      v-bind:title="stat.title"
      v-bind:subtitle="stat.subtitle"
      v-bind:description="stat.description"
    ></cardBar>
    <cardLine
      v-for="stat in Object.values(stats).filter((stat) => stat.type == 'line')"
      v-bind:data="stat.data"
      v-bind:options="stat.options"
      v-bind:key="stat.id"
      v-bind:title="stat.title"
      v-bind:subtitle="stat.subtitle"
      v-bind:description="stat.description"
    ></cardLine>
  </div>
</template>

<script>
import cardLine from "../Trivia/Line";
import cardBar from "../Trivia/Bar.vue";

export default {
  name: "Hotshots",
  data() {
    return {
      stats: [
        {
          id: 0,
          type: "bar",
          title: "Match Winners",
          subtitle: "Mumbai has won most matches followed by CSK",
          description: "But as we've seen, nothing can be predicted!",
          data: {
            labels: [
              "KKR",
              "RCB",
              "CSK",
              "KXI",
              "RR",
              "DD",
              "MI",
              "DC",
              "KT",
              "PW",
              "SH",
              "RP",
              "GL",
            ],
            datasets: [
              {
                label: "Total matches won",
                backgroundColor: "#0085FF",
                data: [68, 70, 79, 63, 63, 56, 80, 29, 6, 12, 34, 5, 9],
                borderColor: "rgba(0,0,0,0.5)",
                lineTension: 0,

                fill: false,
              },
            ],
          },
          options: {
            scales: {
              yAxes: [
                {
                  ticks: {
                    beginAtZero: true,
                    maxTicksLimit: 5,
                  },
                },
              ],
              xAxes: [
                {
                  ticks: {
                    autoSkip: true,
                    autoSkipPadding: 2,
                    maxRotation: 0,
                  },
                },
              ],
            },
            legend: {
              display: false,
            },
            layout: {
              padding: {
                top: 20,
              },
            },
            responsive: true,
            maintainAspectRatio: false,
          },
        },
        {
          id: 1,
          type: "bar",
          title: "The real Hotshots",
          subtitle: "Gayle has the most MOTMs in his pocket!",
          description: "",
          data: {
            labels: [
              "Gayle",
              "Pathan",
              "de Villiers",
              "Warner",
              "R.Sharma",
              "Raina",
              "Rahane",
              "Sehwag",
            ],
            datasets: [
              {
                label: "Man of the Match",
                backgroundColor: "#FF0058",
                data: [20, 16, 15, 14, 13, 13, 12, 11],
                borderColor: "rgba(0,0,0,0.5)",
              },
            ],
          },
          options: {
            scales: {
              yAxes: [
                {
                  ticks: {
                    beginAtZero: true,
                    maxTicksLimit: 5,
                  },
                },
              ],
              xAxes: [
                {
                  ticks: {
                    autoSkip: true,
                    autoSkipPadding: 5,
                    maxRotation: 0,
                  },
                },
              ],
            },
            legend: {
              display: false,
            },
            layout: {
              padding: {
                top: 20,
              },
            },
            responsive: true,
            maintainAspectRatio: false,
          },
        },
      ],
    };
  },
  components: {
    cardBar,
    cardLine,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
