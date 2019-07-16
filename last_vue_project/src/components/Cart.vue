<template>
    <div>
        <div class="text-center list-group-item active">
            <h5>Cart - ${{total}}</h5>
        </div>
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
    props: ['items'],
    computed: {
        total() {
            return this.items.reduce((acc, item) => acc + Number(item.price), 0)
        }
    }
}
</script>

