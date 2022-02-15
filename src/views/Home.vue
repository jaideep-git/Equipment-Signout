<template>
    <div class="home">
        <Header />
        <div class="top-margin"><h2>Equipment Sign Out</h2></div>
        <div class=" main-container row top-margin bottom-margin padding " id="mob-height-3">
            <div class="col l10 s12  ">
                <Tabs :theme="theme" >
                    <TabItem :name="this.$parent.categories[0].name" id="tabItem" >
                        <Assets :assets="this.$parent.categories[0].assets" @addCart="addItemCart" />
                    </TabItem>
                    <TabItem :name="this.$parent.categories[1].name" id="tabItem">
                        <Assets :assets="this.$parent.categories[1].assets" @addCart="addItemCart" />
                    </TabItem>
                    <TabItem :name="this.$parent.categories[2].name" id="tabItem" >
                        <Assets :assets="this.$parent.categories[2].assets" @addCart="addItemCart" />
                    </TabItem>
                    <TabItem :name="this.$parent.categories[3].name" id="tabItem" >
                        <Assets :assets="this.$parent.categories[3].assets" @addCart="addItemCart" />
                    </TabItem>
                    <TabItem :name="this.$parent.categories[4].name" id="tabItem" >
                        <Assets :assets="this.$parent.categories[4].assets" @addCart="addItemCart" />
                    </TabItem>
                    <TabItem :name="this.$parent.categories[5].name" id="tabItem" >
                        <Assets :assets="this.$parent.categories[5].assets" @addCart="addItemCart" />
                    </TabItem>
                    <TabItem :name="this.$parent.categories[6].name" id="tabItem" >
                        <Assets :assets="this.$parent.categories[6].assets" @addCart="addItemCart" />
                    </TabItem>
                </Tabs>
            </div> 
            <div class="col l2 s12  center" id="mob-items">
                <div class="item-counter">
                    <h5>{{ this.$parent.cartItems }}</h5>
                    <h6>Items Taken</h6>
                    <button class="btn checkout-out-button" v-on:click="goCart"><router-link to="/cart">check Out</router-link></button>
                </div>
            </div>
        </div>
        <Footer/>
    </div>
</template>

<script>
// @ is an alias to /src

import Header from "../components/Header.vue";
import Footer from "../components/Footer.vue";
import Assets from "@/components/Assets.vue";
import {
    Tabs,
    TabItem
} from "vue-material-tabs";

export default {
    name: 'Home',
    components: {
        Header,
        Footer,
        Tabs,
        TabItem,
        Assets
    },
    methods: {
        goCart() {
            this.$emit("changeState", {
                state: "toCart",
            });
        },
        addItemCart(e) {
            this.$emit("changeState", {
                state: "addToCart",
                asset: e.asset,
            });
        },
    },
    data: () => ({
        theme: {
        nav: "#008265",
        navItem: "white",
        navActiveItem: "white",
        slider: "#CE93D8",
        arrow: "#f3f3f3",
        },
    })
}

</script>

<style scoped>
.main-container{
    background-color: #F4F5F6;
}
tabs-container{
    background-color: #E9E9E9;
}
.notAvailable-button{
    opacity: 0.8;
}
#tabItem{
    padding:0 3rem;
}
#tabItems{
    height:20rem;
    margin:0 30px;
}
.height-3{
    height:26.6rem;
}
h2{
    font-weight:500;
    color: #008265;
}
.qty{
    padding-left: 50px;
}
.item-not-available{
    color: darkgrey;
    opacity: 0.8;
}
a{
    color:white;
}
.top-margin{
    margin-top:40px ;
}
.top-padding{
    padding-top: 50px;
}
.bottom-margin{
    margin-bottom: 3.9rem ;
}
.item-counter{
    display:flex;
    flex-direction:column;
    align-items: center;
    margin-left: 25px;
    width:170px;
    height:10rem;
    background-color:#E9E9E9;
}
.height-2{
    height:30rem;
}
.padding{
    padding:20px 10px;
}
.checkout-out-button{
    background-color: #008265;
}
</style>