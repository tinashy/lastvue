<template>
    <div class="card" style="width: 18rem; margin-bottom: 1em;">
        <div class="card-body">
            <h5 class="card-title">{{product.title}}</h5>
            <p class="card-text text-muted">${{product.price}}</p>
            <a href="#" class="btn btn-primary">Go somewhere</a>
        </div>
    </div>
</template>

<script>
export default {
    props: ['product']
}
</script>

