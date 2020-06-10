<template>
  <div id="app">
    <div class="d-flex justify-content-center align-items-center">
      <div class="card border-primary mb-3" style="width: 60rem;">
        <div class="card-header">Quizz App</div>
        <div class="card-body" v-for="question in questions" :key="question.id">
          <h4 class="card-title">{{question.question}}</h4>
          <div class="card-text">
            <div class="list-group">
              <a
                href="#"
                class="list-group-item list-group-item-action"
                v-for="suggestion in question.suggestions"
                :key="suggestion"
              >{{suggestion}}</a>
            </div>
          </div>
        </div>
        <div class="card-footer">
          <button class="btn btn-default">Skip</button>
          <button class="btn btn-success">Next</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      questions: [
        {
          id: 1,
          question: "Vue Js is for back end?",
          suggestions: ["true", "false"],
          answer: "False"
        }
      ]
    };
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
