<template>
  <div id="app">
    <dev-menu @toggleMenu="toggleMenu" :menuToggled="menuToggled" :NavItems="NavItems" />
    <button @click="toggleMenu">Dev Menu</button>
  </div>
</template>

<script>
  import DeveloperControl from "@/components/DeveloperControl.vue";
  export default {
    name: "app",
    data() {
      return {
        activeMenu: false,
        NavItems: [
          {
            link: "https://elegant-jackson-350189.netlify.com/",
            destination: "Developer Documents"
          },
          {
            link: "https://github.com/possibly1/DistanceCalc",
            destination: "Calculator Repository"
          },
          {
            link: "https://github.com/possibly1/distanceDocs",
            destination: "Docs Repository"
          },

          {
            link: "https://github.com/possibly1/distanceWidget",
            destination: "Widget Repository"
          }
        ]
      };
    },
    components: {
      "dev-menu": DeveloperControl
    },
    methods: {
      toggleMenu() {
        this.activeMenu = !this.activeMenu;
      }
    },
    computed: {
      menuToggled() {
        return this.activeMenu;
      }
    }
  };
</script>

<style>
  body {
    font-family: "Lato", sans-serif;
  }
</style>
