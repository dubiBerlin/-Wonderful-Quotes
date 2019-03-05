<template>
  <div class="row"></div>
</template>

<script>
export default {
  props: ["quotes"],
  data: function() {
    return {
      quotes: ["Just a quote to see something"],
      maxQuotes: 10
    };
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
}
</style>
