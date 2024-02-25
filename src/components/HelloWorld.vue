<template>
    <div>
        <h1>{{ msg }}</h1>

        <p>
            <a href="https://vitejs.dev/guide/features.html" target="_blank">Vite Documentation</a>
            |
            <a href="https://vuejs.org/v2/guide/" target="_blank">Vue 2 Documentation</a>
        </p>

        <div id="app-3" v-if="seen">Now you see me</div>
        <div id="app-4">
            <ol>
                <li v-for="item in items" :key="item.message">
                    {{ item.message }}
                </li>
            </ol>
        </div>
        <button @click="count++">COUNT is: {{ count }}</button>
        <p>
            <span :title="msg">Edit</span>
            <code>components/HelloWorld.vue</code> to test hot module replacement.
        </p>
    </div>
</template>

<script lang="ts">
export default {
    props: {
        msg: String,
    },
    data() {
        return {
            count: 0,
            items: [
                { message: 'Foo' },
                { message: 'Bar' }
            ]
        };
    },
    computed: {
        seen() {
            return this.count !== 0 && this.count % 5 === 0;
        },
    },
};
</script>

<style scoped>
a {
    color: #42b983;
}
</style>
