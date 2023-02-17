<template>
    <div class="card" style="width: 18rem">
        <div class="card-body">
            <h5 class="card-title">{{ info.number }}</h5>
            <h6 class="card-subtitle mb-2 text-muted">{{ info.name }}</h6>
        </div>
    </div>
</template>
<script>
export default {
    props: {
        info:{
            required: true,
            type: Object
        }
    }
}
</script>
<style></style>
