<template>
  <div class="gift">
      <!-- fita vertical -->
      <div class="gift-tie-1"></div>
      <!-- fita horizontal -->
      <div class="gift-tie-2"></div>
      <!-- A tampa da caixa -->
      <div class="gift-top"></div>
      <!-- corpo do presente -->
      <div class="gift-body"></div>
  </div>
</template>

<script>
export default {
    name:'Gift'
}
</script>

<style>
.gift {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    z-index: 10;
}

.gift-top {
    width: 100px;
    height: 25px;
    background-color: #7aa944;
}

.gift-body {
    width: 90px;
    height: 60px;
    background-color: #5c7e32;
}

.gift-tie-1 {
    position: absolute;
    height: 85px;
    width: 15px;
    background-color: red;
}

.gift-tie-2 {
    position: absolute;
    height: 15px;   
    width: 90px;
    top: 40px;
    background-color: red;
}
</style>