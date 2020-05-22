<template lang="pug">
  .container
    .card
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
    Projects
    Knowledge
    Contact
</template>
<script>
//TODO: Direct to resume builder, and add print to pdf option
import Projects from '~/components/Projects'
import Knowledge from '~/components/Knowledge'
import Contact from '~/components/Contact'
export default {
  components: {
    Projects,
    Knowledge,
    Contact
  },
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

