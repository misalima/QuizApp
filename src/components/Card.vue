<script setup>
  import {useRouter} from "vue-router";
  
  const router = useRouter();
  const {quiz} = defineProps(['quiz']);

  const navigateToQuiz = () => {
    router.push(`/quiz/${quiz.id}`);
  }
  
  
</script>

<template>
    <div class="card" @click="navigateToQuiz">
        <img :src="quiz.img" alt="image">
        <div class="card-text">
            <h2>{{quiz.name}}</h2>
            <p>{{quiz.questions.length}} questions</p>
        </div>
    </div>
</template>

<style scoped>
     /* CARD */
  div.card {
    width: 310px;
    overflow: hidden;
    border-radius: 2%;
    box-shadow: 1px 1px 10px rgba(255, 255, 255, 0.1);
    margin-bottom: 35px;
    margin-right: 20px;
    cursor: pointer;
    padding: 10px;
    background-color: #1f1f1f;
    color: #818181;
    
  }

  .card img {
    width: 100%;
    height: 190px;
    margin: 0;
  }

  .card .card-text {
    padding: 0 5px;
    
  }

  .card-text h2 {
    font-weight: bold;
  }
</style>