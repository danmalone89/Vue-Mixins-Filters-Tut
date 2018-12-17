<script>
export default {
  computed: {
    messageComputed() {
      return this.message
        .split("")
        .reverse()
        .join("");
    },
    wordsComputed() {
      let result = this.words.length;
      return this.words + " (" + result + " )";
    }
  }
}
</script>
