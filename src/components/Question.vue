<template>
    <div class="question">
      <span>{{ question.text }}</span>
      <ul class="answers">
        <li v-for="(answer, i) in question.answers" :key="answer.text" @click="$emit('answered', answer.correct)">
          <span class="number">{{ i + 1 }}</span>
          <span class="text">{{ answer.text }}</span>
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    name: 'QuestionComponent',
    props: {
      question: {
        type: Object,
        required: true
      }
    }
  }
  </script>
  
  <style scoped>
  .question {
    min-height: 200px;
    width: 100%;
    max-width: 700px;
    margin: 0 auto;
    padding: 20px;
    color: #000;
    background-color: #fff;
    border-radius: 20px;
    font-size: 2rem;
  
    display: flex;
    flex-direction: column;
    justify-content: space-around;
  }
  
  ul.answers {
    max-height: 100vh;
    font-size: 1.6rem;
    padding: 0;
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
  }
  
  .answers li {
    margin: 10px;
    background-color: #89c454;
    border-radius: 8px;
    width: 80%;
  
    display: flex;
    flex-direction: column;
  }
  
  .answers .number {
    padding: 10px;
    background-color: #1e9c31;
    color: #fff;
    text-align: center;
    border-top-left-radius: 8px;
    border-top-right-radius: 8px;
  }
  
  .answers .text {
    flex: 1;
    align-self: center;
    padding: 10px;
  }
  
  @media (max-width: 768px) {
    .question {
      min-height: auto;
      font-size: 1.8rem;
    }
  
    ul.answers {
      font-size: 1.4rem;
    }
  
    .answers li {
      margin: 5px;
      width: 90%;
    }
  }
  </style>
  