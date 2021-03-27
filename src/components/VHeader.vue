<template>
  <header class="header">
      <h1 class="header__title">Рейтинг пользователей:</h1>
      <HeaderButton 
      @sort-list="$emit('sort-data')"/>
  </header>
</template>

<script>
import HeaderButton from '@/components/HeaderButton';

export default {
    components: {
        HeaderButton
    }
}
</script>

<style>
 .header {
     display: flex;
     margin: 15px auto 23px;
     max-width: 584px;
     justify-content: space-between;
 }

 .header__title {
    font-size: 24px;
    line-height: 34px;
    color: #2C3E50;
    font-weight: normal;
 }
</style>