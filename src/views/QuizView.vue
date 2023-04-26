<template>
    <div class="container">
        <header>
            <h2>Question 1/3</h2>
            <div class="bar">
                <div class="completion"></div>
            </div>
        </header>
        <div>
            <div class="question-container">
                <h1 class="question">
                    What is the chemical value of table salt?
                </h1>
            </div>
            <div class="options-container">
                <div class="option">
                    <p class="option-label">A</p>
                    <div class="option-value">
                        <p>NaCl</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
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
    height: 100%;
    width: 0%;
    background-color: thistle;
}

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
}

.option-value {
    font-size: 30px;
    width: 100%;
    padding: 0 20px;
}
</style>