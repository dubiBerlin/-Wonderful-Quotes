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
</style>
