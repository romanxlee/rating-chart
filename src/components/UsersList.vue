<template>
  <div class="users">
      <UserCard 
      v-for="(item, index) of users"
      :item="item"
      :index="index"
      :key="index"
      @emit-item="emitData"
      />
  </div>
</template>

<script>
import UserCard from '@/components/UserCard';

export default {
    data() {
        return {
            users: {}
        }
    },
    components: {
        UserCard
    },
    mounted() {
        return fetch('https://my-json-server.typicode.com/Vespand/crmm-tasks/users')
        .then((res) => res.json())
        .then((res) => {
            let sortedData = [...res];
            sortedData.sort((a, b) => a.rating > b.rating ? -1 : 1)
            return this.users = sortedData;
        })
        .catch((err) => console.log(err))
    },
    methods: {
        emitData(item, index) {
            this.$emit('emit-data', item, index)
        }
    }
}
</script>

<style>
.users {
    width: 600px;
    display: flex;
    flex-direction: column;
    margin: 0 auto;
}

.users_sorted {
    flex-direction: column-reverse;
}
</style>