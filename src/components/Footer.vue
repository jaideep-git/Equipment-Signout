<template>
    <footer class="page-footer">
        <p>Copyright © Durham College</p> 
    </footer>
</template>

<script>
export default {
    name: "Footer",
    methods: {
        getProfile() {
            this.$router.push("Profile");
        },
    },
};
</script>

<style>
p{
    font-family: Arial, Helvetica, sans-serif;
    font-size: 20px;
    margin:0
}

.page-footer  {
    display: flex;
    align-items: center;
    margin-top: 5rem;
    justify-content: center;
    height: 80px;
    background-color: #008265;
}

</style>
