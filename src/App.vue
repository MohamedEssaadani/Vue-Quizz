<template>
  <div id="app">
    <div class="d-flex justify-content-center align-items-center">
      <div class="card border-primary mb-3" style="width: 60rem;">
        <div class="card-header">Quizz App</div>
        <div class="card-body">
          <h4 class="card-title">Question</h4>
          <div class="card-text">
            <div class="list-group">
              <a href="#" class="list-group-item list-group-item-action">First Suggestion</a>
              <a href="#" class="list-group-item list-group-item-action">Second Suggestion</a>
              <a href="#" class="list-group-item list-group-item-action">Third Suggestion</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App"
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
