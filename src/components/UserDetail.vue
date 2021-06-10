<template>
  <div>
    <div class="btn-back">
      <router-link to="/" tag="button">Back to List</router-link>
    </div>
    <div class="userWapper">
        <img :src="info.picture">
        <div class="userName">{{ info.firstName }} {{ info.lastName }}</div>
        <div class="userGender">Gender : {{ info.gender }}</div>
        <div class="userBirth">Birth : {{ info.dateOfBirth }}</div>
        <div class="userEmail">E-mail : {{ info.email }}</div>
        <div class="userPhone">Phone : {{ info.phone }}</div>
        <div class="userCountry">Country : {{ info.location.country }}</div>
        <div class="userRegiter">Register : {{ info.registerDate }}</div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'UserDetail',
  props: {
    id: String,
    item: Object
  },
  data(){
    return {
        info: [],
        appId : '60b98fff7381e15ef981c50f'
    }
  },
  mounted(){
    // ajax with axios
    axios.get(`https://dummyapi.io/data/api/user/${this.id}` , {
      'headers' : {
        "app-id" : this.appId
      }
    })
    .then((res) => {
      this.info = res.data;
      console.log( this.info );
    });
  }
}
</script>

<style scoped>
</style>