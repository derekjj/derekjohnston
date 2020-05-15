<template lang="pug">
  .container
    .card
      b-img.card-image-top(:src="this.image" fluid @mouseover="image2" @mouseleave="image1")
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
    Contact
</template>
<script>
//TODO: Take better personal pictures
//TODO: Direct to resume builder, and add print to pdf option
import Projects from '~/components/Projects'
import Contact from '~/components/Contact'
export default {
  components: {
    Projects,
    Contact
  },
  data() {
    return {
      images: ['me1.png', 'me2.png'],
      image: 'me1.png',
    };
  },
  methods: {
    image1() {
      this.image = this.images[0];
    },
    image2() {
      this.image = this.images[1];
    }
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

