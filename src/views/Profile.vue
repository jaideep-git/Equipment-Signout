<template>
    <div>
        <Header />
        <div class="top-margin-2 row 8">
            <input
            type="button"
            class="btn-large edit-profile-button right"
            value="Edit Profile"
            @click="editProfile"
            />
            <h2>Profile</h2>
        </div>  
        <div class="row  profile-container  bottom-margin top-padding-2" id="mob-row">
            <div class="col  s10 l6 student-information "> 
                <h4 >Student Information</h4>
                <div class="profileInfo">
                    <h5><span class="label">First Name-</span> {{this.$parent.borrower.firstName}}</h5>   
                    <h5><span class="label">First Name-</span> {{this.$parent.borrower.lastName}}</h5>   
                    <h5><span class="label">Stundent Id-</span> {{this.$parent.borrower.student_id}}</h5>   
                    <h5><span class="label">DC Mail-</span>{{this.$parent.borrower.dc_email}}</h5>  
                    <h5><span class="label">Secondary Mail-</span>{{this.$parent.borrower.other_email}}</h5>  
                    <h5><span class="label">Program Name-</span>{{this.$parent.borrower.program}}</h5>
                    <h5><span class="label">Program Year-</span>{{this.$parent.borrower.program_year}}</h5>
                    <h5><span class="label">Borrower Status-</span>Good</h5>  
                </div>
            </div>
            <div class="col  s10 l5 student-information "> 
                <h4 >Borrowed Equipments</h4>
                <div class="profileInfo">
                    <table>
                        <tr>
                            <th>Equipments</th>
                            <th>Return Date</th>
                        </tr>
                        <tr v-for="(asset, index) in this.$parent.loggedItems" :key="index">
                            <td>{{asset.description}}</td>
                            <td>{{ asset.due_time}}</td>
                        </tr>
                    </table>
                </div>
            </div>
        </div>
        <Footer />
    </div>
</template>

<script>

import Header from "../components/Header.vue";
import Footer from "../components/Footer.vue";

export default {
    name: 'Profile',
    components: {
        Header,
        Footer
    },
    methods: {
        editProfile () {
            this.$router.push('Profile_Edit');
        },
        cancel () {
            this.$router.push('Profile');
        }
    }
}
</script>

<style scoped>

a{
    color:white;
}
h2{
    font-weight:500;
    color: #008265;
}
#circle {
    width: 150px;
    height: 150px;
    -webkit-border-radius: 100px;
    -moz-border-radius: 25px;
    border-radius: 75px;
}
.circle-margin{
    margin-left:100px;
}
.edit-profile-button{
    background-color: #008265;
}
h5{
    line-height:2;
    font-size:21px;
}
ul.menu li {
    float: left;
    width: 14.28%;
}
.button a {
    color: white;
}
.tab {
    display: none;
}
.student-information{
    background-color:white;
    margin-right: 20px;
}
.dslr {
    display: block;
}
.label{
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    font-weight:600;
}
.profile-container{
    padding-left: 30px;
    background-color: #F4F5F6;

}
.top-margin{
    margin-top:30px ;
}
.top-padding{
    padding-top: 50px;
}

.top-padding-2{
    padding-top: 20px;
    padding-bottom: 20px;
}
.top-margin-2{
    margin-top:50px ;
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
    height:35rem;
}
h4{
    font-size: 23px;
    font-weight: 600;
}
.login{
    line-height:2;
}
.list li{
    line-height: 1.6;
    font-size: 25px;
    list-style-type: none
}
.details{
    color: white;
    display: flex;
    justify-content: space-around;
}
</style>

