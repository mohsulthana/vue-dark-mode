<template>
  <div class="custom-select">
    <select>
      <option value="0">Sport</option>
      <option value="1">NBA</option>
      <option value="2">Volley</option>
      <option value="3">Chess</option>
    </select>
  </div>
</template>

<style>
.custom-select {
  background: #e5e5e5;
  width: 18rem;
  margin: auto .5rem;
  border-radius: 25px !important;
  position: relative;
  font-family: Arial;
}
.custom-select select {
    padding: 5px 8px;
    border: none;
    box-shadow: none;
    background: transparent;
    background-image: none;
    appearance: none;
    -webkit-appearance: none;
}
.custom-select select:focus {
  outline: none;
}
</style>