<template>
  <div class=" wrapper">
    <div class="container-fluid mainBox">
      <div class="row">
        <div class="col-sm-3 menu">
          <img src="../assets/logo.png" id="logo" />
          <h2
            class="menu-item glow"
            v-for="item in tabs"
            v-bind:key="item.id"
            v-on:click="select(item.name)"
          >
            {{ item.name }}
          </h2>
        </div>
        <div class="col-sm-9">
          <component class="pt-5" v-bind:is="selectedComponent"></component>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Seasons from "./Tabs/Seasons.vue";
export default {
  name: "Dashboard",
  data() {
    return {
      title: "IPL - Cricket in the 6th Gear!",
      selected: "Seasons",
      tabs: [
        { id: 0, name: "Seasons" },
        { id: 1, name: "Recap" },
        { id: 2, name: "Hotshots" },
        { id: 3, name: "Action" },
        { id: 4, name: "Extras" },
      ],
    };
  },
  methods: {
    select: function(item) {
      this.selected = item;
    },
  },
  computed: {
    selectedComponent: function() {
      return this.selected.toLowerCase().replace(" ", "");
    },
  },
  components: {
    Seasons,
    Recap: () => import("./Tabs/Recap.vue"),
    Hotshots: () => import("./Tabs/Hotshots.vue"),
    Action: () => import("./Tabs/Action.vue"),
    Extras: () => import("./Tabs/Extras.vue"),
  },
};
</script>

<style scoped>
/* .body {
  background-image: url("../assets/cricket-stadium-vector.jpg");
} */
@import url("https://fonts.googleapis.com/css?family=Ubuntu&display=swap");
#logo {
  max-height: 180px;
  padding-top: 20px;
}
.wrapper {
  /* background-color: cornflowerblue; */
  /* background-image: url("../assets/cricket-stadium-vector.jpg");
  background-repeat: no-repeat;
  background-size: cover; */
  height: 100vh;
  width: 100vw;
  padding-top: 5vh;
}
.row {
  height: 100%;
}

.menu {
  background-color: cornflowerblue;
  background-size: cover;
  height: 100%;
  overflow: hidden;
  font-family: "Ubuntu", sans-serif;
  color: white;
  font-weight: bolder;
}
.menu-item {
  cursor: pointer;
  padding-top: 5px;
}
.contentArea {
  background-color: aliceblue;
}
.mainBox {
  box-shadow: 0 0 5px 5px rgba(0, 0, 0, 0.1);
  background-color: aliceblue;
  height: 90vh;
  width: 95vw;
  overflow-y: scroll;
  margin: 0 auto;
}
.tagline {
  font-weight: bolder;
}
</style>
