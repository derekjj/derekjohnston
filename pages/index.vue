<template lang="pug">
  .container
    Intro
    Projects
    Knowledge
    Contact
</template>
<script>
//TODO: Direct to resume builder, and add print to pdf option
import Intro from "~/components/Intro";
import Projects from "~/components/Projects";
import Knowledge from "~/components/Knowledge";
import Contact from "~/components/Contact";
export default {
  components: {
    Intro,
    Projects,
    Knowledge,
    Contact
  }
};
</script>
<style scoped>
.me {
  width: 800px;
  height: 750px;
  background-image: url("~assets/me.png");
  border-radius: 50%;
}
.p {
  text-indent: 2em;
}
</style>

