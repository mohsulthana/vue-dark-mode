<template>
  <div class="custom-select">
    <select>
      <option value="0">Select car:</option>
      <option value="1">Audi</option>
      <option value="2">BMW</option>
      <option value="3">Citroen</option>
      <option value="4">Ford</option>
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