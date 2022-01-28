<template>
    <div>
        <h1>Your Cart</h1>

        <CartItemCard 
            v-for="product in products"
            :key="product.id"
            :product="product" />


        <CartSummaryPaymentCart />
    </div>
</template>

<script>
import CartItemCard from "../components/cart/CartItemCard.vue"
import CartSummaryPaymentCart from "../components/cart/CartSummaryPaymentCart.vue"

export default {
    components: {
        CartItemCard,
        CartSummaryPaymentCart
    },
    computed: {
        products() {
            return this.$store.getters.cartItems
        }
    }
}
</script>