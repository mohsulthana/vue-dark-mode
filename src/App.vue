<template>
  <div class="app" :class="mode">
    <div class="scrolling-wrapper">
      <Select />
      <Select />
        <Card :cardMode="card-dark"/>
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
      <div class="paddles">
        <button @click="scroll_left" class="left-paddle paddle hidden">
          PREV
        </button>
        <button @click="scroll_right" class="right-paddle paddle">
          >
        </button>
      </div>
    </div>
    <Header />
  </div>
</template>

<script>
import Header from "@/components/Header";
import Card from "@/components/Card";
import Select from "@/components/Select";

export default {
  name: 'app',
  data () {
    return {
      mode: 'light'
    }
  },
  components: {
    Card,
    Select,
    Header
  },
  methods: {
    scroll_left () {
      let content = document.querySelector(".scrolling-wrapper");
      content.scrollLeft -= 50;
    },
    scroll_right () {
      let content = document.querySelector(".scrolling-wrapper");
      content.scrollLeft += 50;
    },
    toggle () {
      if (this.mode === "dark") {
        this.mode = "light"
      } else {
        this.mode = "dark"
      }
    }
  },
}
</script>

<style>
.scrolling-wrapper {
  display: flex;
  overflow-x: auto;
  overflow-y: hidden;
  height: 130px;
  position: relative;
  -webkit-overflow-scrolling: touch;
}
.scrolling-wrapper .card {
  flex: 0 0 auto;
}
.hidden {
	display: none;
}
.paddle {
	position: absolute;
	top: 0;
	bottom: 0;
	width: 3em;
}
.left-paddle {
	left: 0;
}
.right-paddle {
	right: 0;
  position: fixed;
}
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Roboto', 'sans-serif';
}
.app {
  width: 100vw;
  min-height: 100vh;
  background: #f3f3f3;
  color: #152020;
  transition: background 0.3s ease-in-out;
}

.dark {
  background: #192734;
  color: #f3f3f3;
}
</style>
