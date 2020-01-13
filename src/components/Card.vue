<template>
  <div :class="[mode, card]">
    <h6>Time</h6>
    <!-- new line -->
    <div class="team-1">
      <img src="https://brandslogo.net/wp-content/uploads/2013/11/sporting-clube-de-portugal-vector-logo.png" height="20" width="20" alt="">
      <p class="left">Team 1</p><p class="right">Time</p>
    </div>
    <div class="team-2">
      <img src="https://brandslogo.net/wp-content/uploads/2013/11/sporting-clube-de-portugal-vector-logo.png" height="20" width="20" alt="">
      <p class="left">Team 2</p><p class="right">Time</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ['cardMode'],
  data () {
    return {
      mode: 'card',
      card: 'card-light'
    }
  },
  watch: {
    cardMode: function(newVal) {
      if (newVal === 'dark') {
        this.card = 'card-dark'
      } else {
        this.card = 'card-light'
      }
    }
  },
}
</script>

<style>
.card {
  height: 100%;
  width: 150px;
  padding: .5em;
}
.card-light {
  background: #ffffff !important;
  color: #192734 !important;
}
.card-dark{
  background: #192734 !important;
  color: #f3f3f3 !important;
  border: 1px solid white !important;
}
.team-1 img, .team-2 img {
  float: left;
}
p {
  display: inline;
}
.left {
  float: left;
}
.right {
  color: #e5e5e5;
  float: right;
}
</style>