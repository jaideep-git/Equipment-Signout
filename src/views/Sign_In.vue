<template>
    <div>
        <Header/>
        <div class="row top-margin  bottom-margin height-2"   >
            <div class="col l6  s6" id="hero-image">
                <img class="heroImage" src="../assets/hero-image.png" alt="">
            </div>
            <div class="col l6 s12 row height-2">
                <div class="padding-top ">
                <h2 class="left-margin "> Equipment Signt Out</h2>
                <h3 class="left-margin "> Login to Your Account</h3>
                </div>
                <p id="loginCheck"></p>
                <div class="login col l8 s12"> 
                    <label class="label" for="studentId" >Username</label>
                    <input type="text" id="input" name="studentId" v-model="login.student_id" placeholder="username">
                    <label class="label" for="password">Password</label>
                    <input type="password" id="input" name="password" v-model="login.password" placeholder="password">
                    <p class="right no-margin"><router-link class="forgot-password" to="/change_password">Forgot Password?</router-link></p>
                </div>
                <div class="col l12 left-margin">
                    <input type="button" value="Login" class="btn-large login-button" v-on:click="checkCredentials"/>
                </div> 
            </div>
        </div>
        <Footer/>
    </div>
</template>

<script>
import Header from "../components/SignIn_Header.vue";
import Footer from "../components/Footer.vue";


export default {
    name: 'Sign_In',
    components: {
        Header,
        Footer
    },
    data() {
        return {
            login: {
                student_id: "900000009",
                password: "dingo",
            }
        };
    },
    methods: {
        checkCredentials() {
            this.$emit("changeState", {
                state: "login",
                student_id: this.login.student_id,
                password: this.login.password,
            });
        },
    }
}
</script>

<style scoped>
.height-2{
    height:37rem;
}
h2{
    font-weight:600;
    color: #008265;
}
.login-button{
    margin-top:30px;
    width: 10rem;
    background-color:#008265;
}

.forgot-password{
    color:#215C3D
}
h3{
    font-weight:500;
    font-size: 27px;
    color: black;
}
.top-margin{
    margin-top:50px ;
}
.bottom-margin{
    margin-bottom: 50px ;
}
.no-margin{
    margin-top:0;
    margin-bottom:0;
}
.left-margin{
    margin-left: 15px ;
}

.heroImage{
    margin-left: 15px;
}

.login{
    margin-top: 20px;
    margin-left: 20px;
    width:35rem;
    height: 200px;
}
#loginCheck{
    color:red;
    margin-left: 10px;
}
.padding-top{
    padding-top: 1.5rem;
}
#input{
    background-color: white;
    width: 100%;
    padding: 12px 10px;
    margin: 10px 0;
    display: inline-block;
    border: 1px solid #000000;
    border-radius: 0px;
    box-sizing: border-box;
}
.label{
    color: #5B6361;
    font-size: 20px;
}
</style>