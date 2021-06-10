<template>
  <div>
    User List Page
    <br/>
    <User v-for="(item, idx) in items" :key="idx" :item="item" />
      <!-- <div v-for="(item,idx) in items" :key="idx"><router-link :to="`/user/${item.id}`">{{ item.firstName }} {{ item.lastName }}</router-link></div> -->
  </div>
</template>

<script>
import axios from 'axios';
import User from '@/components/User.vue'

export default {
  name: 'UserList',
  components: {
      User
  },
  props: {
    
  },
  data(){
    return {
      items : [],
      appId : '60b98fff7381e15ef981c50f'
    }
  },
  mounted(){
    axios.get('https://dummyapi.io/data/api/user?limit=10' , {
      'headers' : {
        "app-id" : this.appId
      }
    })
    .then((res) => {
      this.items = res.data.data;
      console.log( this.items );
    });
  }
}
</script>

<style scoped>

</style>