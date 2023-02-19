<script setup>
    import BirdTypes from '../components/BirdTypes.vue'
</script>

<template>
    <div id="Choose">
        <button @click="Val = !Val">Är du bekant med fåglar?</button>
        <h1 v-if="Val">Jag är rutinerad</h1>
        <h1 v-else>Jag är helt ny</h1>
    </div>
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
                Val: true
            }
        },
        data() {
            return {
                message: 'Fåglar i sverige!',
                birds: []
            }
        },

        components: { bird: BirdTypes },
        mounted() {
            this.fetchData()
        },
        methods: {
            async fetchData() {
                const res = await fetch('bird.json')
                const result = await res.json()
                this.birds = result
            }
        },

    }
</script>

<style scoped></style>
