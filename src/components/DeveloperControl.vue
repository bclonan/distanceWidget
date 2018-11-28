<template>
  <div class="sidenav" v-if="menuToggled === true" :class="[ menuToggled === true ? 'is-active' : '']">
    <a href="javascript:void(0)" class="closebtn" @click.prevent="toggleMenu">&times;</a>
    <h1 class="titleBlock">Destinations</h1>
    <a v-for="item in NavItems" :key="item.id" :href="item.link">{{item.destination}}</a>
  </div>
</template>

<script>
  export default {
    name: "DeveloperControler",
    props: ["menuToggled", "NavItems"],
    methods: {
      toggleMenu() {
        this.$emit("toggleMenu");
      }
    }
  };
</script>

<style scoped>
  .sidenav {
    height: 100%;
    width: 0;
    position: fixed;
    z-index: 1;
    top: 0;
    left: 0;
    background-color: blueviolet;
    overflow-x: hidden;
    transition: 0.5s;
    padding-top: 60px;
  }

  .sidenav a {
    padding: 8px 8px 8px 32px;
    text-decoration: none;
    font-size: 1.2rem;
    color: #f1f1f1;
    display: block;
    transition: 0.3s;
  }

  .sidenav a:hover {
    color: #000000;
  }

  .sidenav .closebtn {
    position: absolute;
    top: 0;
    right: 25px;
    font-size: 36px;
    margin-left: 50px;
  }

  #main {
    transition: margin-left 0.5s;
    padding: 16px;
  }

  @media screen and (max-height: 450px) {
    .sidenav {
      padding-top: 15px;
    }
    .sidenav a {
      font-size: 18px;
    }
  }

  .is-active {
    width: 250px;
  }
  .titleBlock {
    text-align: center;
    text-decoration: underline;
    color: black;
  }
</style>