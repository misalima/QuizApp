<script setup>
    
    const {question} = defineProps(['question']);

    const emit = defineEmits(["selectOption"]);
    
    const emitSelectedoption = (isCorrect) => {
        emit("selectOption", isCorrect);
    }
</script>

<template>
    <div class="question-container">
        <h1 class="question">
            {{question.text}}
        </h1>
    </div>
    <div class="options-container">
        <div v-for="option in question.options" :key="option.id" class="option" @click="emitSelectedoption(option.isCorrect)">
            
            <p class="option-label">{{option.label}}</p>
            <div class="option-value">
                <p>{{option.text}}</p>
            </div>
        </div>
    </div>
</template>

<style scoped>
    .question-container {
        margin-top: 20px;
    }

    .question {
        font-size: 40px;
        margin-bottom: 20px;
    }

    .option {
        display: flex;
        margin-bottom: 20px;
        cursor: pointer;
    }

    .option-label {
        background-color: bisque;
        width: 50px;
        height: 50px;
        font-size: 30px;
        display: flex;
        align-items: center;
        justify-content: center;
        color: black;
        transition: background-color 0.3s;
    }

    .option-label:hover {
        background-color: rgb(248, 206, 155);
    }



    .option-value {
        font-size: 30px;
        width: 100%;
        padding: 0 20px;
        transition: color 0.2s;
    }

    .option-label:hover~.option-value {
        color: white;
    }
</style>