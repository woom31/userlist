<template>
    <div>
        <router-link :to="`/user/${item.id}`">
            <div class="userBox">
                <img :src="item.picture" class="userImg" alt="user image">
                <div class="userName">{{ item.firstName }}{{ item.lastName }}</div>
                <div class="userEmail">{{ item.email }}</div>
            </div>
        </router-link>
    </div>
</template>

<script>
export default {
    name: 'User',
    props: {
        item: Object
    },
    data() {
        return{
            
        }
    }
}
</script>

<style scoped>

</style>