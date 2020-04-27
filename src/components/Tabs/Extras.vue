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
    <cardPie
      v-for="stat in Object.values(stats).filter((stat) => stat.type == 'pie')"
      v-bind:data="stat.data"
      v-bind:options="stat.options"
      v-bind:key="stat.id"
      v-bind:title="stat.title"
      v-bind:subtitle="stat.subtitle"
      v-bind:description="stat.description"
    ></cardPie>
  </div>
</template>

<script>
import cardDoughnut from "../Trivia/Doughnut.vue";
import cardPie from "../Trivia/Pie.vue";

export default {
  name: "Extras",
  data() {
    return {
      stats: [
        {
          id: 0,
          type: "doughnut",
          title: "Wickets",
          subtitle: "The bowling team leaves no chance!",
          description:
            "No surprise that getting caught is the most common dismissal!",
          data: {
            labels: [
              "Caught",
              "Bowled",
              "Run Out",
              "LBW",
              "Stumped",
              "Caught-n-Bowled",
            ],
            datasets: [
              {
                label: "Dismissal: ",
                backgroundColor: [
                  "#FF001D",
                  "#00FFA3",
                  "#6300FF",
                  "#00B1FF",
                  "#FFBA00",
                  "cyan",
                ],
                data: [3245, 1028, 583, 326, 187, 148],
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
          type: "doughnut",
          title: "Extra Runs",
          subtitle: "Occasionally the bowlers mess up",
          description: "6,259 such runs have been given!",
          data: {
            labels: ["Legbyes", "Wides", "Byes", "No-Balls"],
            datasets: [
              {
                label: "Dismissal: ",
                backgroundColor: ["#FF001D", "#FFBA00", "#6300FF", "#00FFA3"],
                data: [1950, 3496, 320, 493],
              },
            ],
          },
          options: {
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
    cardPie,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
