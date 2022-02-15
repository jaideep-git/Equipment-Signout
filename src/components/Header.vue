<template>
    <div class="nav">
        <div class="nav-wrapper row ">
            <div class="col s4 l2 height valign-wrapper ">
                <a href="#" class="logo">
                    <router-link to="/home"><img class="logo" src="../assets/logo.png" alt=""/></router-link>
                </a>
            </div>
            <div class="col l10 s8 nav-width  ">
                <ul id="nav-list" class="right">
                    <li><router-link class="font" to="/home"><i class="fas fa-home"></i> Home</router-link></li>
                    <li><router-link class="font" to="/profile"><i class="fas fa-user-circle"></i> Profile</router-link></li>
                    <li><router-link class="font" to="/cart"><i class="fas fa-shopping-cart"></i> Cart</router-link></li>
                    <li><a href="" class="font" v-on:click="logOut"><i class="fas fa-sign-out"></i> Log Out</a></li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Header",
    methods: {
        logOut() {
            this.$router.push("/");
        },
    },
};
</script>

<style scoped>
#nav-list {
    display: flex;
    gap: 25px;
    align-items: center;
    color: white;
    margin-right: 20px;
}
li {
    color: white;
}
.height {
    height: 100px;
}
.log-out-button {
    font-size: 17px;
    background-color: #1bb36c;
}
.nav {
    box-shadow: 0 2px 2px 0 rgb(0 0 0 / 14%), 0 3px 1px -2px rgb(0 0 0 / 12%),
    0 1px 5px 0 rgb(0 0 0 / 20%);
}
.font {
    font-family: Arial, Helvetica, sans-serif;
    color: white;
    font-size: 19px;
    font-weight: lighter;
}
.font:hover {
    color: rgb(0, 0, 0, 0.6);
}
.list-padding {
    padding-top: 9px;
}

.nav-width {
    display: flex;
    justify-content: end;
    height: 100px;
    background: url(../assets/nav-width.png);
}
</style>
