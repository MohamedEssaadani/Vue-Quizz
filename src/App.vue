<template>
  <div id="app">
    <div class="d-flex justify-content-center align-items-center">
      <div class="card border-primary mb-3" style="width: 60rem;">
        <div class="card-header">Quizz App</div>
        <div class="card-body" v-for="question in questions.slice(i,j)" :key="question.id">
          <h4 class="card-title">{{question.question}} {{j}} / {{questions.length}}</h4>
          <div class="card-text">
            <div class="list-group">
              <a
                href="#"
                :class=" select ? suggestion.css : 'list-group-item list-group-item-action' "
                v-for="suggestion in question.suggestions"
                :key="suggestion.suggestion"
                @click="answerSelected()"
              >{{suggestion.suggestion}}</a>
            </div>
          </div>
        </div>
        <div class="card-footer">
          <button class="btn btn-default" @click="nextQuestion()">Skip</button>
          <button class="btn btn-success" @click="nextQuestion()">Next</button>
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
          suggestions: [
            {
              suggestion: "true",
              css: "alert alert-danger"
            },
            {
              suggestion: "false",
              css: "alert alert-success"
            }
          ]
        },
        {
          id: 4,
          question: "GraphQL is a query language for API's?",
          suggestions: [
            {
              suggestion: "true",
              css: "alert alert-success"
            },
            {
              suggestion: "false",
              css: "alert alert-danger"
            }
          ]
        },
        {
          id: 2,
          question: "Select a PHP framework from the list",
          suggestions: [
            {
              suggestion: "Laravel",
              css: "alert alert-success"
            },
            {
              suggestion: "Express Js",
              css: "alert alert-danger"
            },
            {
              suggestion: "Spring",
              css: "alert alert-danger"
            }
          ]
        }
      ],
      i: 0,
      j: 1,
      select: false
    };
  },
  methods: {
    nextQuestion() {
      this.select = false;
      this.i += 1;
      this.j += 1;
    },
    answerSelected() {
      this.select = !this.select;
    },
    check(suggestion) {
      return suggestion.status === "correct"
        ? "alert alert-success"
        : "alert alert-danger";
    }
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
