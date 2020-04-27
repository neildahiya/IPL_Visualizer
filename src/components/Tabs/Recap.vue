<template>
  <div class="">
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
import cardBar from "../Trivia/Bar.vue";
import cardLine from "../Trivia/Line.vue";

export default {
  name: "Recap",
  data() {
    return {
      stats: [
        {
          id: 0,
          type: "line",
          title:
            Math.floor(
              (17922 +
                16349 +
                18878 +
                21142 +
                21333 +
                22204 +
                18926 +
                18353 +
                18858) /
                9
            ) + " Runs!",
          subtitle: "Average runs in a season!",
          description:
            "So it wouldn't be wrong to say that IPL is Cricket on Performance Boosters!",
          data: {
            labels: [
              "2008",
              "2009",
              "2010",
              "2011",
              "2012",
              "2013",
              "2014",
              "2015",
              "2016",
            ],
            datasets: [
              {
                label: "Total runs scored",
                backgroundColor: "#9E48B7",
                data: [
                  17922,
                  16349,
                  18878,
                  21142,
                  21333,
                  22204,
                  18926,
                  18353,
                  18858,
                ],
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
                    autoSkipPadding: 20,
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
          title: "Definitely not like a test match!",
          subtitle: "You wouldn't need to wait to see some action",
          description: "Runs per ball",
          data: {
            labels: [
              "2008",
              "2009",
              "2010",
              "2011",
              "2012",
              "2013",
              "2014",
              "2015",
              "2016",
            ],
            datasets: [
              {
                label: "Runs scored per ball",
                backgroundColor: "#d0466b",
                data: [1.32, 1.2, 1.3, 1.24, 1.2, 1.22, 1.32, 1.34, 1.33],
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
                    autoSkipPadding: 20,
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
  "vue/no-use-v-if-with-v-for": [
    "error",
    {
      allowUsingIterationVar: false,
    },
  ],
  components: {
    cardBar,
    cardLine,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
