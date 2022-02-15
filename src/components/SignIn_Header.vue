<template>
    <nav>
        <div class="nav-wrapper row ">
            <div class="col s4 l2 height valign-wrapper ">
                <img class="logo" src="../assets/logo.png" alt="">
            </div>
            <div class="nav-width col l10 s8  height"></div>
        </div>
    </nav>
</template>

<script>
export default {
    name: "Header",
    methods: {
    
}
};
</script>

<style scoped>
nav {
    height: 100px;
}
.top-margin1{
margin-top: 20px;
margin-right: 20px;
}
.height {
    height: 100px;
}
.link{
    font-size: 25px;
    
}
.logo{
    margin-left: 10px;
}

.nav-width{
    background: url(../assets/nav-width.png);
}
</style>
