<template>
  <div>
    <div class="row">
      <div class="col-sm"></div>
      <div class="col-sm">col-sm</div>
      <div class="col-sm">col-sm</div>
    </div>
    <br><br>
    <div class="row">
      <div class="col-8"></div>
      <div class="col-4">
        <button @clck="start">Start</button>
        <button @clck="Attack">Attack</button>
        <button @clck="Special">Special Attack</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      player: [{name: "", hp: "", image: ""},{name: "", hp: "", image: ""},{name: "", hp: "", image: ""},{name: "", hp: "", image: ""},{name: "", hp: "", image: ""}],
      monster: [{name: "", hp: "", image: ""},{name: "", hp: "", image: ""},{name: "", hp: "", image: ""},{name: "", hp: "", image: ""},{name: "", hp: "", image: ""}],
    };
  },
  methods: {
    randomno: function (min, max) {
      return Math.max(Math.floor(Math.random() * max) + 1, min);
    },
  },
  start: function () {
      this.aplayer = this.player[this.randomno(0,4)-1]
  },
  Attack: function () {},
  Special: function () {},
};
</script>

<style>
</style>