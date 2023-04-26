<script setup>
    import QuizHeader from "../components/QuizHeader.vue";
    import Question from "../components/Question.vue";
    import { useRoute } from "vue-router";
    import quizzes from "../data/quizes.json"
    import { ref, computed } from "vue";

    const route = useRoute();
    const quizId = parseInt(route.params.id);
    const currentQuestionIndex = ref(0);
    const quiz = quizzes.find((q) => q.id === quizId);


    const questionStatus = computed(() => `${currentQuestionIndex.value}/${quiz.questions.length}` );
    const barProgress = computed(() => `${currentQuestionIndex.value / quiz.questions.length * 100}%`)

</script>

<template>
    <div>
        <QuizHeader :questionStatus="questionStatus" :barProgress="barProgress"/>
        <div>
            <Question :question="quiz.questions[currentQuestionIndex]" :options="quiz.options" />
        </div>
        <button @click="currentQuestionIndex++">Next question</button>
    </div>
</template>

