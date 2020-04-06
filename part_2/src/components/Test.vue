<template>
    <div class="test">
        <h3>{{ judul }}</h3>
        <hr>
        <ol>
            <li v-for="item in todos" :key="item.name">
                {{ item.name }}
            </li>
        </ol>
    </div>
</template>

<script>
export default {
    name: 'Test',
    props: {
        judul: String
    },
    data: function () {
        return {
            todos: [
                {name: 'Install Vue-CLI'},
                {name: 'Initiate new project'},
                {name: 'Run project'}
            ]
        }
    }
}
</script>

<style scoped>

</style>