<template>
  <div id="app">
    <div id="menu">
      <ul>
        <li>
          <a href="#p1">Section 1</a>
        </li>
        <li>
          <a href="#p2">Section 2</a>
        </li>
        <li>
          <a href="#p3">Section 3</a>
        </li>
      </ul>
    </div>
    <full-page ref="fullpage" :options="options" id="fullpage">
      <div class="section" v-for="(item, index) in divNumber" :key="index">
        <p>Section {{item}}</p>
      </div>
    </full-page>
  </div>
</template>
<script>
export default {
  created() {
    this.getHashFunc();
  },
  mounted() {},
  destroyed() {},
  data() {
    return {
      divNumber: 3,
      options: {
        menu: "#menu",
        dragAndMove: true,
        resetSliders: true,
        navigation: true,
        anchors: ["p1", "p2", "p3"],
        sectionsColor: [
          "#41b883",
          "#ff5f45",
          "#0798ec",
          "#41b883",
          "#ff5f45",
          "#0798ec"
        ]
      }
    };
  },
  methods: {
    getHashFunc() {}
  }
};
</script>
<style lang="scss">
@import "https://fonts.googleapis.com/css?family=Modak|Odibee+Sans&display=swap";
body {
  padding: 0rem;
  margin: 0rem;
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    width: 100%;
    height: auto;
    #fullpage {
      position: relative;
      width: 100%;
      height: auto;
      .section {
        position: relative;
        width: 100%;
        height: 100%;
        height: auto;
        p {
          position: absolute;
          top: 50%;
          left: 50%;
          transform: translate(-50%, -50%);
          margin: 0rem;
          color: #fff;
          font-size: 5rem;
          font-family: "Modak", cursive;
        }
      }
    }
  }
  #menu {
    position: absolute;
    width: 100%;
    top: 0rem;
    left: 0rem;
    z-index: 99999;
    ul {
      margin: 1rem 0rem 0rem 0rem;
      padding: 0rem;
      list-style: none;
      li {
        display: inline-block;
        margin-right: 0.5rem;
        a {
          display: inline-block;
          padding: 0.7rem 1rem;
          color: #1b262c;
          text-decoration: none;
          background-color: rgba(0, 0, 0, 0.09);
          border-radius: 0.2rem;
          &:target {
            color: #f00;
          }
        }
      }
    }
  }
}
</style>
