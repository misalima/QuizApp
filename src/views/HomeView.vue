<script setup>
import q from "../data/quizes.json";
import { ref, watch } from "vue";
import Card from "../components/Card.vue"
import { RouterLink } from "vue-router"
const quizzes = ref(q);
const search = ref("");

watch(search, () => {
    quizzes.value = q.filter(quiz => quiz.name.toLowerCase().includes(search.value.toLowerCase()));
})

</script>
<template>
    <div class="container">
        <header>
            <h1>Quizzes</h1>
            <input v-model.trim="search" type="text" placeholder="Search...">
        </header>
        <div class="options-container">
            <RouterLink class="card-wrapper" v-for="quiz in quizzes" to="/card">
                <Card  :key="quiz.id" :quiz="quiz" />
            </RouterLink>
        </div>
    </div>
</template>

<style scoped>
.container {
    max-width: 1000px;
    margin: 0 auto;
    
}

header {
    margin-bottom: 10px;
    margin-top: 30px;
    display: flex;
    align-items: center;
}

header h1 {
    font-weight: bold;
    margin-right: 30px;
}

input {
    border: none;
    background-color: #ffffff;
    padding: 10px;
    border-radius: 5px;
    color: black;
}

.card-wrapper {
    text-decoration: none;
    
}

.options-container {
    display: flex;
    flex-wrap: wrap;
    margin-top: 40px;
}
</style>