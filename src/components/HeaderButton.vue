<template>
  <button 
  @click="$emit('sort-list')"
  class="header__button">
  </button>
</template>

<script>
export default {
    
}
</script>

<style>
    .header__button {
        width: 34px;
        height: 34px;
        border-radius: 8px;
        background-image: url('../assets/sort.svg');
        background-position: center;
        background-repeat: no-repeat;
        background-color: #fff;
        border: 1px solid rgba(44, 62, 80, 0.67);
    }

    .header__button:hover {
        cursor: url('../assets/mouse.svg'), auto;
    }
</style>