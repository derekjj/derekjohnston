<template lang="pug">
  .container
    .row
      nuxt-link(to="/projects/MintbeanHackathons")
        button.m-2.btn.btn-outline-success Back     
      component(:is="dynamicComponent")
</template>
<script>
import LiveCSSEditor from "~/components/MintbeanHackathons/LiveCSSEditor.vue";
import InteractiveCalculator from "~/components/MintbeanHackathons/InteractiveCalculator.vue";
import HackTheResume from "~/components/MintbeanHackathons/HackTheResume.vue";
import ResumeBuilder from "~/components/MintbeanHackathons/ResumeBuilder.vue";
import MarkdownEditor from "~/components/MintbeanHackathons/MarkdownEditor.vue";
export default {
  params: { project: String },
  components: {
    LiveCSSEditor,
    InteractiveCalculator,
    HackTheResume,
    ResumeBuilder,
    MarkdownEditor
  },
  data() {
    return {
      dynamicComponent: this.$route.params.project
    };
  },
  mounted() {
    console.log(this.$route.params.project);
  }
};
</script>