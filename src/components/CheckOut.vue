<template>
    <div class="checkout-container bottom-margin">
        <div class="row" id="mob-height-2">
            <div class="row reciept center s12 l12 height-3 ">
                <div class=" col l5 reciept-box center">
                    <div class="h3"><h3>Sign Out Reciept</h3></div>
                    <div class="signout-details">
                        <div>
                            <table>
                                <tr v-for="(asset, index) in this.$parent.assets" :key="index">
                                    <td>{{asset.asset_description}}</td>
                                </tr>
                            </table>
                        </div>
                        <h5>Sign Out Date:</h5>
                        <p>Thu Dec 09 2021 14:40:27 GMT-0500 (Eastern Standard Time)</p>
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
        </div>
    </div>
</template>

<script>
export default {
    name: "Checkout",
    components: {},
};
</script>

<style scoped>
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
}
.reciept {
    display: flex;
}

h5 {
    font-family: "Times New Roman", Times, serif;
}

hr {
    color: grey;
}
</style>
