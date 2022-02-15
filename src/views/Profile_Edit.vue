<template>
    <div>
        <Header />
        <div class="top-margin"><h2>Profile Edit</h2></div>
        <div class="row profile-container height-2 bottom-margin">
            <div class="login col l4 s12"> 
                <label class="label" for="firtName">First Name</label>
                <input type="text" v-model="borrower.firstName" id="input" name="firstName" placeholder="username">
                <label class="label"  for="firtName">Last Name</label>
                <input type="text" v-model="borrower.lastName" id="input" name="firstName" placeholder="username">
                <label class="label" for="password">Secondary Email</label>
                <input type="text" v-model="borrower.other_email" id="input" name="password" placeholder="Secondary Email">
                <label class="label" for="userName">Old Password</label>
                    <input type="password" id="input" v-model="borrower.password_old" name="userName" placeholder="Old password">
                    <label class="label"  for="password">New Password</label>
                    <input type="password" id="input" v-model="borrower.password_new" name="password" placeholder="New password">
                    <label class="label"  for="password">Confirm password</label>
                    <input type="password" id="input"  v-model="borrower.password_confirm" name="password" placeholder="Confirm password">
                    <p id="passCheck"></p>
                <div class="top-margin">
                <button class="btn update-button" v-on:click="updateProfile">Update</button>
                <button class="btn grey left-margin" v-on:click="cancel">Cancel</button>
                </div>
            </div>
        </div>
        <Footer/>
    </div>
</template>

<script>

import Header from "../components/Header.vue";
import Footer from "../components/Footer.vue";

export default {
    name: 'Profile_Edit',
    components: {
        Header,
        Footer
    },
    data() {
        return {
            borrower: {
                firstName:this.$parent.borrower.firstName,
                lastName:this.$parent.borrower.lastName,
                other_email:this.$parent.borrower.other_email,
                password_old:"",
                password_new:"",
                password_confirm:""
            },
        };
    },
    methods: {
        updateProfile () {
            if(this.borrower.password_new == this.borrower.password_confirm){
                this.$emit("changeState", {
                    state: "update",
                    borrower:{
                        firstName:this.borrower.firstName,
                        lastName:this.borrower.lastName,
                        other_email:this.borrower.other_email,
                        password_old:this.borrower.password_old,
                        password_new:this.borrower.password_new
                    }
            });
            }else{
                document.getElementById("passCheck").innerHTML="password do not match"
            }
        },
        cancel () {
            this.$router.push('Profile');
        }
    }
}
</script>

<style scoped>
h2{
    font-weight:500;
    color: #008265;
}

a {
    color: white;
}
.tab {
    display: none;
}

.dslr {
    display: block;
}
.update-button{
    background-color: #008265;
}
.top-margin{
    margin-top:30px ;
}
.top-padding{
    padding-top: 50px;
}
.top-margin-2{
    margin-top:50px ;
}
.float{
    float: right;
    margin-right: 0;
}
.bottom-margin{
    margin-bottom: 30px ;
}
.bottom-margin-2{
    margin-bottom: 50px ;
}
.no-margin{
    margin-right: 0;
}
.left-margin{
    margin-left: 20px ;
}
.height-2{
    height:47rem;
}
.profile-container{
    padding-left: 30px;
    background-color: #F4F5F6;
}
#input{
    background-color: white;
    width: 100%;
    padding: 12px 5px;
    margin: 8px 0;
    display: inline-block;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
}
.label{
    color: black;
    font-size: 20px;
}
.login{
    margin-top: 20px;
    margin-left: 20px;
    width:35rem;
    height: 200px;
}
::placeholder {
    color: black;
    opacity: 0.7; /* Firefox */
}
#passCheck{
    color:red;
    font-size:17px;
}
</style>