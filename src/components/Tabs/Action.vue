<template>
  <div class>
    <cardDoughnut
      v-for="stat in Object.values(stats).filter(
        (stat) => stat.type == 'doughnut'
      )"
      v-bind:data="stat.data"
      v-bind:options="stat.options"
      v-bind:key="stat.id"
      v-bind:title="stat.title"
      v-bind:subtitle="stat.subtitle"
      v-bind:description="stat.description"
    ></cardDoughnut>
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
import cardDoughnut from "../Trivia/Doughnut.vue";
import cardBar from "../Trivia/Bar.vue";

export default {
  name: "Action",
  data() {
    return {
      stats: [
        {
          id: 0,
          type: "doughnut",
          title: "21226 Boundaries!",
          subtitle: "Don't worry! You read that right!",
          description: "5813 sixes & 15413 fours!",
          data: {
            labels: ["6", "4", "1"],
            datasets: [
              {
                label: "Runs scored per ball",
                backgroundColor: ["#FF001D", "#9CFF00", "#6300FF"],
                data: [5813, 15413, 50107],
              },
            ],
          },
          options: {
            legend: {
              display: false,
            },
            layout: {
              padding: {
                bottom: 10,
              },
            },
            responsive: true,
            maintainAspectRatio: false,
          },
        },
        {
          id: 1,
          type: "bar",
          title: "Toss isn't always the deciding factor!",
          subtitle: "Match can stil go any team's way",
          description: "Only ~50% of Toss Winners win the game",
          data: {
            labels: ["Toss Winner Won", "Toss Winner Lost"],
            datasets: [
              {
                label: "Toss Result",
                backgroundColor: ["#007EFF", "#FF8100"],
                data: [291, 286],
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
  components: {
    cardDoughnut,
    cardBar,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
