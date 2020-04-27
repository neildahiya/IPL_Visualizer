<template>
  <div class="">
    <cardLine
      v-for="stat in Object.values(stats).filter((stat) => stat.type == 'line')"
      v-bind:data="stat.data"
      v-bind:options="stat.options"
      v-bind:key="stat.id"
      v-bind:title="stat.title"
      v-bind:subtitle="stat.subtitle"
      v-bind:description="stat.description"
    ></cardLine>
    <cardBar
      v-for="stat in Object.values(stats).filter((stat) => stat.type == 'bar')"
      v-bind:data="stat.data"
      v-bind:options="stat.options"
      v-bind:key="stat.id"
      v-bind:title="stat.title"
      v-bind:subtitle="stat.subtitle"
      v-bind:description="stat.description"
    ></cardBar>
  </div>
</template>

<script>
import cardLine from "../Trivia/Line.vue";
import cardBar from "../Trivia/Bar.vue";

export default {
  name: "Seasons",
  data() {
    return {
      stats: [
        {
          id: 0,
          type: "line",
          title: "Almost Everyday!",
          subtitle:
            "You wouldn't need to wait to watch your team beat the one you hate.",
          description: "60+ matches each season",
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
                label: "Matches in each season",
                // backgroundColor: "rgba(150,190,74,1)",
                data: [60, 59, 60, 76, 74, 73, 60, 57, 58],
                borderColor: "#FFD000",
                backgroundColor: "#FFD000",
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
                    beginAtZero: false,
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
          title: "Winners",
          subtitle: "Your team has probably already won it!",
          description:
            "Mumbai, Chennai and Kolkata have each won 2 times! (2016 data)",
          data: {
            labels: [
              "Mumbai",
              "Kolkata",
              "Chennai",
              "Hyderabad",
              "Deccan Ch.",
              "Rajasthan",
              "Others",
            ],
            datasets: [
              {
                backgroundColor: [
                  "#006BFF",
                  "#8F00FF",
                  "#FFCB00",
                  "#AEDBFF",
                  "#00FFA7",
                  "#FF0067",
                  "#C73862",
                ],
                data: [2, 2, 2, 1, 1, 1, 0],
              },
            ],
          },
          options: {
            legend: {
              display: false,
            },
            responsive: true,
            maintainAspectRatio: false,
          },
        },
      ],
    };
  },
  components: {
    cardLine,
    cardBar,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
