<template>
  <div class="modal">
      <div class="modal__content">
        <div class="modal__head">
            <h2 class="modal__title">Профиль пользователя:</h2>
            <img 
            @click="$emit('close-modal')"
            src="../assets/close.svg" alt="Закрыть окно" class="modal__close">
        </div>


        <div class="modal__wrapper">
            <div 
            v-bind:style="{backgroundImage: 'url(' + item.avatar + ')'}"
            v-bind:class="{first: index === 0, second: index === 1, third: index === 2}"
            class="modal__avatar">
            </div>

            <div class="modal__bio">
                <h4 class="modal__title-bio">Имя:</h4>
                <p class="modal__text">{{ item.name }}</p>
                <h4 class="modal__title-bio">Баллы:</h4>
                <p class="modal__text">{{ item.rating }}</p>
                <h4 class="modal__title-bio">Позиция в рейтинге:</h4>
                <p class="modal__text">{{ index + 1 }}</p>
            </div>
        </div>
        

        <div class="modal__about">
            <h4 class="modal__title-bio">О себе</h4>
            <p class="modal__text">{{ item.description }}</p>
        </div>
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
    .modal {
        position: fixed;
        top: 0;
        left: 0;
        display: none;
        width: 100%;
        height: 100%;
        align-items: center;
        justify-content: center;
        background: rgba(0, 0, 0, 0.2);
    }

    .modal.modal_is-opened {
        display: flex;
    }

    .modal__content {
        width: 478px;
        min-height: 281px;
        padding: 27px 16px 21px 24px;
        background-color: #fff;
        display: flex;
        flex-direction: column;
        box-sizing: border-box;
    }

    .modal__head {
        display: flex;
        justify-content: space-between;
        margin-bottom: 26px;
    }

    .modal__title {
        font-weight: normal;
    }

    .modal__close {
        width: 32px;
        height: 32px;
    }

    .modal__close:hover {
        background-color: rgba(0, 0, 0, 0.07);
        border-radius: 16px;
        cursor: url('../assets/mouse.svg'), auto;
    }

    .modal__wrapper {
        display: flex;
        max-width: 352px;
    }

    .modal__avatar {
        width: 129px;
        height: 129px;
        border-radius: 50%;
        margin-right: 37px;
        background-size: cover;
    }

    .modal__about {
        margin-top: 17px;
    }

    .modal__title-bio {
        font-size: 18px;
        line-height: 18px;
        color: #2C3E50;
        margin-bottom: 4px;
        font-weight: normal;
    }

    .modal__text {
        font-size: 16px;
        line-height: 18px;
        color: #2C3E50;
    }
</style>