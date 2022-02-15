<template>
    <div class="height">
        <table >
        <tr>
            <th>Equipment</th>
            <th>Available Quantity</th>
        </tr>
        <tr v-for="(asset, index) in this.assets" :key="index">
            <td   class="active" :class="asset.asset_class" >
            {{ asset.asset_description }}
            </td>
            <td class="qty" :class="asset.asset_class">
            {{ asset.assets_count_available }}
            </td>
            <td v-if="asset.assets_available == true"><button class="btn checkout-out-button"   @click="addCart(asset)" >+ Add</button></td>
            <td v-else>
            <button class="btn not-active "> +Add</button>
            
            </td>
        </tr>
        </table>
    </div>
</template>

<script>
export default {
    name: "Assets",
    props: {
    assets: Array,
},
methods: {
    addCart(item) {
        item.assets_available = false;
        this.$emit("addCart", { state: "addToCart", asset: item });
    },
},
};
</script>

<style scoped>
.height{
    margin-top: 10px;
    height:320px;
    width: 100%;
    overflow:scroll;
    overflow-x: hidden;
}
.not-active {
    color: white;
    background-color: rgb(206, 203, 203);
}
.checkout-out-button{
    background-color: #008265;
}
a{
    color: white;
}
.qty{
    padding-left: 50px;
}
</style>