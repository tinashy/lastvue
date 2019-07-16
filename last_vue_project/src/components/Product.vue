<template>
    <div class="card" style="width: 18rem; margin-bottom: 1em;">
        <div class="card-body">
            <h5 class="card-title">{{product.title}}</h5>
            <p class="card-text text-muted">${{product.price}}</p>
            <button :disabled="isInCart" @click="$emit('add-to-cart', product)" class="btn btn-primary btn-sm">Add To Cart</button>
        </div>
    </div>
</template>

<script>
export default {
    props: ['product', 'isInCart']
}
</script>

