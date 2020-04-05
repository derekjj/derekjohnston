<template lang="pug">
  .container
    .card
      .card-body.m-3
        | Greetings, My name is Derek and I am a passionate software developer!
        br
        br
        p
          i “Any fool can write code that a computer can understand. Good programmers write code that humans can understand.”
          br
          | ― Martin Fowler
        br
        | Currently developing projects with Docker, NuxtJS, VueJS, Flutter(Dart), Ruby on Rails & PHP.
        br
        br
        p
          b Seeking employment opportunities remotely or Toronto to Durham and surrounding areas.
        br
        br
        a(href="/DerekJohnstonNoCell.pdf") Resume
</template>
<script>
export default {
  head() {
    return {
      titleTemplate: "%s"
    };
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
  text-indent:  2em;
}
</style>

