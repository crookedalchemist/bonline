<template>
    <div class="toolbar">
        <div class="logo"><img src="../assets/bonlinelogo.svg" alt=""></div>
        <div class="user_select">
            <i class="fa fa-bell-o" aria-hidden="true">
                <span class="position-absolute top-0 start-100 translate-middle p-2 bg-danger border border-light rounded-circle">
                    <span class="visually-hidden">New alerts</span>
                </span>
            </i>
            <select v-model='users'>
                <option selected v-for='users in userdata' v-bind:value='users' :key="users">{{users.first_name}}</option>
            </select>
        </div>
    </div>
</template>
<script>
export default {
    name: 'ToolBar',
    props: {
        usersdata: Array,
        value: String
    },
    data(){
        return{
            users: []
        }
    },
    watch: {
    users: function() {
        this.$emit('input', this.users);
    }
  }
}
</script>
<style scoped>
    
</style>