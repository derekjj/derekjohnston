<template lang="pug">
  .container.p-4
    .card
      .card-title
        h1 Live Markdown Editor
    .card
      .card-body
        .row
          .col-6
            b-form-textarea.vh-100(
              id="textarea"
              v-model="text"
              rows="20"
              placeholder="Enter something...")
          .col-6.text-left
            vue-markdown(:source="text", xhtml-out: true)
</template>
<script>
import VueMarkdown from "vue-markdown"; // production
export default {
  name: "MarkDownEditor",
  components: {
    VueMarkdown,
  },
  data() {
    return {
      text: "The time of **NOW** is :",
    };
  },
};
</script>