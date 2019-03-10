<template>
  <div class="row">
    <div class="col-sm-12">
      <h3>Quotes Added</h3>
      <div class="progress">
        <div class="progress">
          <div
            class="progress-bar"
            role="progressbar"
            aria-valuenow="60"
            aria-valuemin="0"
            aria-valuemax="100"
            :style="{ width: (quoteCount/maxQuotes)*100+'%',color:'black'}"
          >{{quoteCount}} / {{maxQuotes}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["maxQuotes", "quoteCount"],
  created() {
    console.log("maxQuotes: ", this.maxQuotes);
  }
};
</script>

<style>
.panel-body {
  font-family: "Arizona", cursive;
  font-size: 24px;
  color: #6e6e6e;
}

.quote {
  cursor: pointer;
}

.quote:hover {
  background-color: #ffe2e2;
}
</style>
