<template>
    <div class="about">
        <h1>This is an about page</h1>
    </div>
    <div id="welcome">
        <input v-model="name" />
        <h1>Välkommen {{ a }}!</h1>
    </div>
    <div id="text">
        <p v-bind:class="{ a: a > 5 && a < 7 }">Fågel</p>
    </div>
</template>

<script>
    export default {
        data() {
            return { name: '' }
        },
        computed: {
            a() {
                return this.name
            }
        },
        data() {
            return {
                a: 6
            }
        }
    }
</script>

<style scoped>
    .a {
        background-color: blue;
    }
</style>
