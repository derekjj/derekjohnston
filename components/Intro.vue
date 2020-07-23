<template lang="pug">
  transition(name="fade")  
    .card(v-if="isShowing")
      b-img.card-image-top(:src="require('!!url-loader?limit=0!~/assets/tech-bg.jpg')" fluid)
      .card-body.m-3
        p
          i “Any fool can write code that a computer can understand. Good programmers write code that humans can understand.”
          br
          | ― Martin Fowler
        br
        | Currently developing projects with Docker, NuxtJS, VueJS, ReactJS, NodeJS, Flutter(Dart), Ruby on Rails & PHP.
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
  data() {
    return {
      isShowing: false
    };
  },
  mounted() {
    this.isShowing = true;
  }
};
</script>