<template>
  <div class="wrapper">
    <div class="container-fluid p-0 mainBox">
      <b-navbar class="mobile-nav" toggleable="lg" type="dark" variant="primary">
        <b-navbar-brand href="/">
          <img id="logo" src="../assets/logo.png" />IPL
        </b-navbar-brand>
        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav>
            <b-nav-item
              href="#"
              v-for="item in tabs"
              v-bind:key="item.id"
              v-on:click="select(item.name)"
              v-bind:class="[{ selectedComp: item.name === selected }]"
            >{{ item.name }}</b-nav-item>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
      <div class="row occupy-vertical">
        <div class="col-sm-3 menu">
          <img src="../assets/logo.png" alt="logo" class="img-fluid" id="logo" />

          <p
            class="menu-item h2"
            v-for="item in tabs"
            v-bind:key="item.id"
            v-on:click="select(item.name)"
            v-bind:class="[{ selectedComp: item.name === selected }]"
          >{{ item.name }}</p>
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
        { id: 4, name: "Extras" }
      ]
    };
  },
  methods: {
    select: function(item) {
      this.selected = item;
    },
    toggleView: function() {}
  },
  computed: {
    selectedComponent: function() {
      return this.selected.toLowerCase().replace(" ", "");
    }
  },
  components: {
    Seasons,
    Recap: () => import("./Tabs/Recap.vue"),
    Hotshots: () => import("./Tabs/Hotshots.vue"),
    Action: () => import("./Tabs/Action.vue"),
    Extras: () => import("./Tabs/Extras.vue")
  }
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css?family=Ubuntu&display=swap");

#logo {
  max-height: 180px;
  padding: 10px;
}
.wrapper {
  height: 100vh;
  width: 100vw;
}
.mainBox {
  box-shadow: 0 0 5px 5px rgba(0, 0, 0, 0.1);
  background-color: aliceblue;
  height: 100vh;
  width: 100vw;
  overflow-y: scroll;
  overflow-x: hidden;
  margin: 0 auto;
}
/* To make div occupy full height */
.occupy-vertical {
  height: 100%;
}
/* Side menu */
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

/* Chart Area */
.contentArea {
  background-color: aliceblue;
}

.selectedComp {
  background-color: rgba(0, 0, 0, 0.1);
}

/* Media Queries */
@media screen and (max-width: 700px) {
  .menu {
    width: 100%;
    height: auto;
    position: relative;
  }

  div.content {
    margin-left: 0;
  }
  #logo {
    max-width: 60px;
  }
  .menu {
    display: none;
  }
  .wrapper {
    padding: 0vh;
  }
}
@media screen and (min-width: 700px) {
  .mobile-nav {
    display: none;
  }
}
</style>
