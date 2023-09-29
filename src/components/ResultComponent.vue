<template>
  <div class="result">
    <div class="title">{{ results[resultIndex].title }}</div>
    <div class="desc">
      {{ results[resultIndex].desc }}
    </div>
  </div>
</template>

<script>
export default {
  props: [ "tottalCorrect", "results" ],
  computed: {
    resultIndex() {
      let index = 0;
      this.results.forEach((element, i) => {
        if (element.min <= this.tottalCorrect && element.max >= this.tottalCorrect) {
          index = i;
        }
      });

      return index;
    }
  }
};
</script>

