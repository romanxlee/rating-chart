<template>
  <div 
  @click="$emit('emit-item', item, index)"
  class="user-card">
      <div 
      v-bind:style="{backgroundImage: 'url(' + item.avatar + ')'}"
      v-bind:class="{first: index === 0, second: index === 1, third: index === 2}"
      class="user-card__avatar"></div>
      <div class="user-card__bio">
          <h2 class="user-card__title">Пользователь</h2>
          <p class="user-card__name">{{ item.name }}</p>
      </div>
      <div class="user-card__rating">
          <img src="../assets/star.svg" alt="" class="user-card__star">
          <p class="user-card__count">{{ item.rating }}</p>
      </div>
  </div>
</template>

<script>
export default {
    props: {
        item: {
            type: Object
        }, 
        index: {
            type: Number
        }
    }
}
</script>

<style>
    .user-card {
        display: flex;
        padding: 14px;
        max-width: 600px;
        height: 88px;
        box-sizing: border-box;
    }

    .user-card:hover {
        background-color: rgba(0, 0, 0, 0.07);
        border-radius: 10px;
        cursor: url('../assets/mouse.svg'), auto;
    }

    .user-card__avatar {
        width: 60px;
        height: 60px;
        background-size: cover;
        border-radius: 50%;
    }

    .first {
        box-shadow: 0 0 0 4px #FDD835;
    }

    .second {
        box-shadow: 0 0 0 4px #90A4AE;
    }

    .third {
        box-shadow: 0 0 0 4px #795548;
    }

    .user-card__rating {
        display: flex;
        margin-left: auto;
        align-items: center;
        justify-content: space-between;
        width: 50px;
    }

    .user-card__title {
        font-size: 18px;
        line-height: 18px;
        color: #2C3E50;
        font-weight: normal;
        margin-bottom: 2px;
    }


    .user-card__name {
        font-size: 18px;
        line-height: 18px;
        color: #2C3E50;
    }

    .user-card__bio {
        margin-left: 24px;
        align-self: center;
    }

    .user-card__count {
        font-size: 18px;
        line-height: 18px;
        color: #2C3E50;
    }
</style>