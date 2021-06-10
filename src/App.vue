<template>
  <div id="app">
    <router-view></router-view>
    <!-- router-view 가 렌더링이 되지 않음 -->
    <!-- <UserList/> -->
  </div>
</template>

<script>
// import UserList from '@/components/UserList.vue'

export default {
  name: 'App',
  components: {
    // UserList
  }
}
</script>

<style>

</style>
