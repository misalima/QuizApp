<script setup>
    import {RouterLink} from "vue-router";

    const {quizQuestionLength, numberOfCorrectAnswers } = defineProps(["quizQuestionLength", "numberOfCorrectAnswers"]);

</script>
<template>
    <div class="results">
       <p>Your Results...</p>
       <h1>{{ numberOfCorrectAnswers }}/{{ quizQuestionLength }}</h1> 
       <RouterLink to="/">Go Back</RouterLink>
    </div>
</template>
<style scoped>
    .results {
        text-align: center;
        padding: 100px 30px;
    }

    p {
        font-size: 32px;
    }

    h1 {
        font-size: 72px;
        margin-bottom: 50px;
    }

    a {
        padding: 10px;
        background-color: beige;
        border-radius: 6px;
        text-decoration: none;
        color: black;
        font-weight: bold;
    }
    a:hover {
        background-color: bisque;
    }
</style>