<script setup>
    import QuizHeader from "../components/QuizHeader.vue";
    import Question from "../components/Question.vue";
    import Results from "../components/Result.vue";
    import { useRoute } from "vue-router";
    import quizzes from "../data/quizes.json"
    import { ref, computed } from "vue";

    const route = useRoute();
    const quizId = parseInt(route.params.id);
    const currentQuestionIndex = ref(0);
    const quiz = quizzes.find((q) => q.id === quizId);
    const numberOfCorrectAnswers = ref(0);
    const showResults = ref(false);

    const questionStatus = computed(() => `${currentQuestionIndex.value}/${quiz.questions.length}` );
    const barProgress = computed(() => `${currentQuestionIndex.value / quiz.questions.length * 100}%`);

    const onOptionSelected = (isCorrect) => {
        if(isCorrect) {
            numberOfCorrectAnswers.value++;
        }
        currentQuestionIndex.value++;
        if(quiz.questions.length === currentQuestionIndex.value) {
            showResults.value = true;
        }
        
        
    }

</script>

<template>
    <div>
        <QuizHeader :questionStatus="questionStatus" :barProgress="barProgress"/>
        <div>
            <Question v-if="!showResults" :question="quiz.questions[currentQuestionIndex]" @selectOption="onOptionSelected" />
            <Results v-else :quizQuestionLength="quiz.questions.length" :numberOfCorrectAnswers="numberOfCorrectAnswers" />
        </div>
        
    </div>
</template>

