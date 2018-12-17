<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <h1>Filters & Mixins</h1>
        <!-- Exercise 1) -->
        <!-- Build a local Filter which reverses the Text it is applied on -->
        <h4>Exercise 1 (Filter)</h4>
        <input type="text" v-model="message">
        <p>Result: {{ message | reverseMessage }}</p>
        <hr>
        <!-- Exercise 2 -->
        <!-- Build a global Filter which counts the length of a word and it appends it -->
        <!-- Like this: "Test" => Gets Filtered to => "Test (4)" -->
        <h4>Exercise 2 (Filter)</h4>
        <input type="text" v-model="words">
        <p>Result: {{ words | countLength }}</p>
        <hr>
        <!-- Exercise 3 -->
        <!-- Do the same as in Exercises 1 & 2, now with Computed Properties -->
        <h4>Exercise 3.1 (Computed Properties)</h4>
        <input type="text" v-model="message">
        <p>Result: {{ messageComputed }}</p>
        <br>
        <h4>Exercise 3.2 (Computed Properties)</h4>
        <input type="text" v-model="words">
        <p>{{ wordsComputed }}</p>
        <!-- Exercise 4 -->
        <!-- Share the Computed Property rebuilding Exercise 2 via a Mixin -->
      </div>
    </div>
  </div>
</template>

<script>
import myMixin from "./MyMixin.vue";

export default {
  mixins: [myMixin],
  data() {
    return {
      message: "Message",
      reversedMessage: "",
      words: "Words"
    };
  },
  filters: {
    reverseMessage(value) {
      return value
        .split("")
        .reverse()
        .join("");
    }
  }
  // Imported via mixin
  //   computed: {
  //     messageComputed() {
  //       return this.message
  //         .split("")
  //         .reverse()
  //         .join("");
  //     },
  //     wordsComputed() {
  //       let result = this.words.length;
  //       return this.words + " (" + result + " )";
  //     }
  //   }
};
</script>

<style>
</style>
