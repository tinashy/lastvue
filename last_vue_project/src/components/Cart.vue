<template>
    <div>
        <h5>Cart</h5>
        <ul class="list-group" v-for="item in items" :key="item.id">
            <li class="list-group-item">
                {{item.title}} - ${{item.price}}
                <button @click="$emit('remove-from-cart', item)" type="button" class="btn btn-outline-danger btn-sm float-right">Remove From Cart</button>
            </li>
        </ul>
    </div>
</template>


<script>
export default {
    props: ['items']
}
</script>

