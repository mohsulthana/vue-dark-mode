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
        <button @click="scroll_right" class="right-paddle paddle">
          <img src="https://previews.123rf.com/images/eljanstock/eljanstock1811/eljanstock181109222/111703684-right-arrow-vector-icon-isolated-on-transparent-background-right-arrow-transparency-logo-concept.jpg" height="40" width="40" alt="">
        </button>
        <button class="scoreboard-btn">FULL SCOREBOARD</button>
    </div>
    <Toggle :mode="mode" @toggle="toggle"/>
    <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Pariatur, est suscipit. Enim aliquid ratione quidem deserunt officia alias dolore voluptatem itaque consequatur quia. Quos non alias quidem illo minima sequi.</p>
    <p style="display: block"><strong>Press 't' to switch the toggle</strong></p>
  </div>
</template>

<script>
import Card from "@/components/Card";
import Select from "@/components/Select";
import Toggle from '@/components/Toggle';


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
    Toggle
  },
  created () {
    window.addEventListener('keyup', this.keyPress)
  },
  methods: {
    keyPress (e) {
      if (e.key === 't') {
        this.toggle()
      }
    },
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
.scrolling-wrapper {
  display: flex;
  overflow-x: auto;
  overflow-y: hidden;
  height: 130px;
  position: relative;
  -webkit-overflow-scrolling: touch;
}
.scoreboard-btn {  
  position: sticky;
  right: 20;
}
.scrolling-wrapper .card {
  flex: 0 0 auto;
}
.hidden {
	display: none;
}
.paddle {
	position: relative;
	top: 0;
	bottom: 0;
	width: 3em;
}
.left-paddle {
	left: 0;
}
.right-paddle {
	right: 0;
  padding: auto 20px;
  width: 300px;
  position: sticky;
}
</style>
