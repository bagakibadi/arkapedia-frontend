<template>
    <div class="nav-menu-user">
        <div class="nav-user-toko">
            <div class="icon-toko">
                <i class="fas fa-store"></i>
            </div>
            <div class="toko-menu-link">
                <router-link to="/profileStore">Toko</router-link>
            </div>
        </div>
        <div class="nav-user-profile">
            <router-link to="/profileStore" class="icon-toko">
                <img :src="user.image" :alt="user.image">
            </router-link>
            <div class="toko-menu-link">
                <router-link to="/profile">{{ user.name }}</router-link>
            </div>
        </div>
    </div>
</template>

<script>
import { mapActions, mapState } from 'vuex';

export default {
  name: 'User_section',
  mounted() {
    this.getUserById();
  },
  computed: {
    ...mapState('user', ['user']),
  },
  methods: {
    ...mapActions('user', ['getUserById']),
  },
};
</script>

<style scoped>
.nav-menu-user::after{
    content: '';
    position: absolute;
    top:15px;
    height: 0;
    border-left: 1px solid #cacaca;
    width:100%;
    height: 50%;
}
.nav-menu-user{
    display: flex;
    flex: 1.8;
    background-color: rgb(255, 255, 255);
    height: 100%;
    position: relative;
}

.nav-user-toko{
    width:50%;
    height: 100%;
    background-color: rgb(255, 255, 255);
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
}
.icon-toko img{
    width: 35px;
    height: 35px;
    border-radius: 50%;
    /* background-color: rgba(0, 0, 0, 0.1); */
}

.icon-toko{
    margin-left: 10px;
    width: 35px;
    height: 35px;
    border-radius: 50%;
    background-color: rgba(0, 0, 0, 0.1);
    display: flex;
    justify-content: center;
    align-items: center;
}

.icon-toko i{
    color: #03ac0e;
}
.toko-menu-link{
    width:130px;
    height: 40px;
    display: flex;
    align-items: center;
    background-color: rgb(255, 255, 255);
    position: relative;
    z-index: 1;
}
.toko-menu-link a{
    text-decoration: none;
    color: rgb(100, 100, 100);
    padding-left: 10px;
    width: 100%;
    background-color: rgb(255, 255, 255);
    font-size: 13px;
}
.nav-user-profile{
    width:50%;
    height: 100%;
    background-color: rgb(255, 255, 255);
    display: flex;
    align-items: center;
    padding-left: 10px;
}
</style>
