<template>
    <div>
        <Header />
        <div class="top-margin"><h2>Your Cart</h2></div>
        <div class="row  height-2 cart-container top-margin bottom-margin padding " id="mob-height">
            <table class=" highlight striped ">
                <thead>
                    <tr class="">
                        <th>Equipment</th>
                        <th>Sign Out</th>
                        <th>Return Date</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="(asset, index) in this.$parent.cart" :key="index">
                        <td class="left">{{ asset.asset_description }}</td>
                        <td class="">{{newDate()}}</td>
                        <td class="">{{dueDate() }}</td>
                        <td class="red-text">
                            <i @click="$emit('deleteItem', index)" class="material-icons pointer">delete</i>
                        </td>
                    </tr>
                </tbody>
            </table>
            <button class="btn right checkout-out-button top-margin-3" v-on:click="goReserve">CheckOut</button>
            <input
            type="button"
            class="btn right top-margin-3 cancel lighten-1 right-margin"
            value="Add More"
            @click="goMain"
            />
        </div>
        <Footer />
    </div>
</template>

<script>
import Header from "../components/Header.vue";
import Footer from "../components/Footer.vue";

export default {
    name: "Cart",
    components: {
        Header,
        Footer,
    },
    methods: {
        goMain() {
            this.$emit("changeState", {
                state: "toMain",
            });
        },
        goReserve() {
            this.$emit("changeState", {
                state: "toReserve",
            });
        },
        currentDate() {
            return new Date();
        },
        home() {
            this.router.push("Home");
        },
        newDate() {
            let date = new Date();
            let year = new Intl.DateTimeFormat('en', { year: 'numeric' }).format(date);
            let month = new Intl.DateTimeFormat('en', { month: 'numeric' }).format(date);
            let day = new Intl.DateTimeFormat('en', { day: '2-digit' }).format(date);
            return (`${day}-${month}-${year}`);
        },
        dueDate() {
            let date = new Date();
            date.setHours(date.getHours() + 72);
            let year = new Intl.DateTimeFormat('en', { year: 'numeric' }).format(date);
            let month = new Intl.DateTimeFormat('en', { month: 'numeric' }).format(date);
            let day = new Intl.DateTimeFormat('en', { day: '2-digit' }).format(date);
            return (`${day}-${month}-${year}`);
        }
    },
    data() {
        return {
            component: "",
        };
    },
};
</script>

<style scoped>
.checkout-out-button {
    width: 10rem;
    background-color: #008265;
}
.cancel {
    color: black;
    background-color: silver;
}
a{
    color: white;
}
tr:nth-child(even) {
    background-color: beige;
}
.color-blue {
    color: steelblue;
}
.top-margin {
    margin-top: 4rem;
}
.top-margin-3 {
    margin-top: 35px;
}
.top-padding {
    padding-top: 50px;
}
.cart-container {
    background-color: #f4f5f6;
}
.top-margin-2 {
    margin-top: 50px;
}

.bottom-margin {
    margin-bottom: 5.5rem;
}
.bottom-margin-2 {
    margin-bottom: 50px;
}
h2 {
    font-weight: 500;
    color: #008265;
}
.no-margin {
    margin-right: 0;
}
.left-margin {
    margin-left: 20px;
}
.right-margin {
    margin-right: 20px;
}
.height-2 {
    height: 27rem;
}
.list li {
    line-height: 1.6;
    font-size: 25px;
    list-style-type: none;
}
.padding {
    padding: 20px 7rem;
}
</style>
