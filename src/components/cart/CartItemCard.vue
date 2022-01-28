<template>
    <div class="cart-item-card">
        <div class="header">
            <h3>{{ product.name }}</h3>
            <h4>In Cart: {{ product.quantity }}</h4>
            <h4>Total Cost: {{ item_cost.toFixed(2) }}</h4>
        </div>

        <p>{{ description }}</p>
    </div>
</template>

<script>
export default {
    props: ['product'],
    computed: {
        description() {
            return this.product.description.substring(0, 120)
        },
        item_cost() {
            return this.product.quantity * this.product.price
        }
    }
}
</script>

<style scoped>
.cart-item-card {
    width: 90%;
    margin: 5%;
    background-color: white;
    box-shadow: 0 0 5px gray;
    border-radius: 5px;
    padding: 10px;
    text-align: left;
}

.header {
    display: flex;
    justify-content: space-around;
}



@media (min-width: 500px) {
    .cart-item-card {
        width: 500px;
        margin: 10px auto;
    }
}
</style>