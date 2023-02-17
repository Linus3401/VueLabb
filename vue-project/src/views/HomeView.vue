<script setup>
    import BirdTypes from '../components/BirdTypes.vue'
</script>

<template>
    <h1 class="bird-title">{{ message }}</h1>
    <div id="info">
        <div class="container text-center">
            <div class="row align-items-start">
                <bird v-for="bird in birds" ::key="bird.id" :info="bird" />
                <Bird />
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        data() {
            return {
                message: 'Fåglar i sverige!',
                birds: []
            }
        },

        components: { 'bird': BirdTypes },
        mounted() {
            this.fetchData()
        },
        methods: {
            async fetchData() {
                const res = await fetch('bird.json')
                const result = await res.json()
                this.birds = result
            }
        }
    }
</script>
<style scoped></style>
