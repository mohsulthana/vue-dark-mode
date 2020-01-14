<template>
  <div class="app" :class="mode">
    <div class="scrolling-wrapper">
        <button @click="scroll_left" class="left-paddle paddle hidden">
          <img src="https://image.flaticon.com/icons/svg/271/271220.svg" height="40" width="40" alt="">
        </button>
        <Select />
        <Card/>
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
          <img src="https://image.flaticon.com/icons/svg/271/271228.svg" height="40" width="40" alt="">
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
      content.scrollLeft -= 700;
      if (content.scrollLeft == 0) {
        document.querySelector(".left-paddle").classList.add('hidden')
      } else{
        document.querySelector(".left-paddle").classList.remove('hidden');
      }
    },
    scroll_right () {
      let content = document.querySelector(".scrolling-wrapper");
      content.scrollLeft += 700;
      console.log(content.scrollLeft)
      if(content.scrollLeft == 0 || content.scrollLeft > 0) {
        document.querySelector(".left-paddle").classList.remove('hidden')
      } else {
        document.querySelector(".left-paddle").classList.add('hidden');
      }
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
@import url('https://fonts.googleapis.com/css?family=Roboto+Condensed&display=swap');
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Roboto Condensed', 'sans-serif';
}
.app {
  width: 100vw;
  min-height: 100vh;
  line-height: 20px;
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
  overflow: auto;
  height: 120px;
  position: relative;
  -webkit-overflow-scrolling: touch;
  transition: transform .4s ease-in;
  scroll-behavior: smooth;
}
::-webkit-scrollbar {
    width: 0px;
    background: transparent; /* make scrollbar transparent */
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
  padding: auto 20px;
  width: 300px;
  z-index: 9999999;
  position: sticky;
}
.right-paddle {
	right: 0;
  padding: auto 20px;
  width: 300px;
  position: sticky;
}
</style>
