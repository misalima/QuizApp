<script setup>

    const {questionStatus, barProgress} = defineProps(['questionStatus', 'barProgress']);

</script>

<template>
    <header>
        <h2>Question {{questionStatus}}</h2>
        <div class="bar">
            <div class="completion" :style="{width: barProgress}"></div>
        </div>
    </header>
</template>

<style scoped>
    header {
        margin-bottom: 10px;
        margin-top: 30px;
    }

    .bar {
        width: 300px;
        height: 50px;
        border: 3px solid bisque;
    }

    .completion {
        width: 0%;
        height: 100%;
        background-color: thistle;
    }
</style>