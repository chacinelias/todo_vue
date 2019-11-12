<template>
    <div class="container">
        <button class="btn" @click.prevent="handleClick">
            <i class="fas fa-plus fa-2x"></i>
        </button>
    </div>
</template>

<script>
export default {
    name: 'AddTodo',
    props: [],
    methods: {
        handleClick() {
            this.$emit("addTodo")
        }
    }
}
</script>