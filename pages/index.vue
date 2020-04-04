<template lang="pug">
  .container-fluid
    .card
      .card-header
        | Greetings, My name is Derek and I am a passionate software developer!
      .card-body
        .card-title
          .p Albert Einstein once said 
            i “It has become appallingly obvious that our technology has exceeded our humanity.” 
            | Technology is all around us, so I choose to embrace it, there is no hiding from it.
          br
          | Currently developing side projects with Nuxt.js / Vue.js / Flutter / Ruby on Rails & PHP.
          br
          br
          | The next subject I am looking to do research with is Docker.
          br
          br
          p
            b Seeking employment opportunities in Toronto to Durham and surrounding areas.
          p
            b With a healthy work/life balance and learning resources.
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

