<template>
	<div>
		<Header/>
		<div class="top-margin"><h2>Change Password</h2></div>
		<div class="row height-2  profile-container top-margin-2 bottom-margin-2">
			<div class="col l4  s12">
				<label class="label" for="userName">Old Password</label>
				<input type="text" id="input" name="userName" placeholder="username">
				<label class="label" for="password">New Password</label>
				<input type="text" id="input" name="password" placeholder="Secondary Email">
				<label class="label" for="password">Confirm password</label>
				<input type="text" id="input" name="password" placeholder="password">
				<div class="top-margin">
					<button class="btn update-button" v-on:click="changePassword">Update</button>
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
    methods: {
        changePassword() {
            this.$router.push('/');
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

.profile-container{
    background-color: #F4F5F6;
}
.update-button{
    background-color:#008265;
}
a {
    color: white;
}
.top-margin{
    margin-top:30px ;
}
.top-padding{
    padding-top: 50px;
}
.top-margin-2{
    padding-top: 30px;
    padding-left: 20px;
    margin-top:30px ;
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
.height-2{
    height:33rem;
}
#input{
    background-color: white;
    width: 100%;
    padding: 12px 20px;
    margin: 8px 0;
    display: inline-block;
    border: 0.5px solid black;
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
.left-margin{
    margin-left: 20px ;
}
.top-margin{
    margin-top: 40px ;
}
</style>