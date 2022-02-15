<template>
    <div class="home">
        <Header />
        <div class="row top-margin bottom-margin " id="mob-height-2">
            <div class="row reciept center s12 l12">
                <div class=" col l5 reciept-box center">
                    <div class="h3"><h3>Sign Out Reciept</h3></div>
                    <div div class="signout-details">
                        <div>
                            <h5>Items Taken</h5>
                            <table>
                                <tr v-for="(asset, index) in this.$parent.cart" :key="index">
                                    <td>{{asset.asset_description}}</td>
                                </tr>
                            </table>
                        </div>
                        <h5>Sign Out Date:</h5>
                        <p>{{currentDate()}}</p>
                    </div>
                </div>
                <div class=" col l7">
                    <h4>Thank You! <i class="fas fa-check-circle"></i></h4>
                    <h5>
                        You now have 20 minutes to go to room L123 and pick up your
                        equipment. You will need your student card.
                    </h5>
                </div>
            </div>
            <input
            type="button"
            class="btn right top-margin-3 cancel  right-margin"
            value="Go to home"
            @click="goHome"
            />
        </div>
        <Footer/>
    </div>
</template>

<script>
import Header from "../components/Header.vue";
import Footer from "../components/Footer.vue";

export default {
    name: 'Reserve',
    components: {
        Header,
        Footer
    },
    methods:{
        currentDate(){
            return new Date()
        },
        goHome(){
            this.$emit("changeState", {
                state: "toHome",
            });
        }
    }
}
</script>

<style scoped>

.cancel{
    background-color: #008265;
}
th,td{
    text-align: center;
}
.top-margin {
    margin-top: 50px;
}
.bottom-margin {
    margin-bottom: 50px;
}
.height-2 {
    height: 23rem;
}
.height-3 {
    height: 25rem;
}
.h3 {
    margin-bottom: 2rem;
}
.padding {
    padding: 20px 7rem;
}
.signout-details {
    padding: 0 5rem;
}
.checkout-container {
    padding: 20px 20px;
    background-color: #f4f5f6;
}
.reciept-box {
    background-color: white;
    border-right:1px solid grey;
}
.reciept {
    display: flex;
}
th,h5 {
    font-family: "Times New Roman", Times, serif;
}
hr {
    color: grey;
}

</style>