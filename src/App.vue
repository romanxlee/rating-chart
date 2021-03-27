<template>
  <div id="app">
    <VHeader 
      @sort-data="sortData"
    />
    <UsersList 
      v-bind:class="{ 'users_sorted': isSorted}"
      @emit-data="openModal"
    />
    <UserModal 
      v-bind:item="item"
      v-bind:index="index"
      v-bind:class="{ 'modal_is-opened': modalOpen }"
      @close-modal="closeModal"
    />
  </div>
</template>

<script>
import VHeader from '@/components/VHeader';
import UsersList from '@/components/UsersList';
import UserModal from '@/components/UserModal';

export default {
  name: 'App',
  components: {
    VHeader,
    UsersList,
    UserModal
  },
  methods: {
    openModal(item, index) {
      this.modalOpen = true;
      this.item = item;
      this.index = index;
    },
    closeModal() {
      this.modalOpen = false;
    },
    sortData() {
      this.isSorted = !this.isSorted
    }
  },
    data() {
      return {
        modalOpen: false,
        isSorted: false,
        item: {},
        index: 0
      }
  }
}
</script>

<style>

* {
  margin: 0;
  padding: 0;
}

#app {
  margin: 0 auto;
  max-width: 960px;
  font-family: Avenir, sans-serif;
  font-style: normal;
}
</style>
