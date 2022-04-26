<template>
    <div>
        <ul>

            <ItemApp
            v-for="(todoItem, i)  of todos"  :key="todoItem.id" todo_prop.sync="todoItem"
            v-bind:todoItem="todoItem"
            v-bind:index="i"
            v-on:removeTodoItem="removeTodoItem"

            />
        </ul>
    </div>
</template>
<script>
    import ItemApp from '@/components/ItemApp'
    export default {
        props: ['todos'],
        components:{
            ItemApp
        },
        methods: {
            removeTodoItem(id) {
                this.$emit('remove-todo', id)
            }
        }
    }
</script>
<style scoped>
    ul {
        list-stile: none;
        margin: 0;
        padding: 0;
    }
</style>