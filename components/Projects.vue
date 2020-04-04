<template lang="pug">
  .row
    .col-md-6.my-3(v-for="project in projects")
      .card.h-100
        .card-header.h-100
          a(:href="project.address", v-if="project.address.length > 0")
            img.card-img-top.mh-100(:src="project.image")
          div(v-else)
            img.card-img-top.mh-100(:src="project.image")
        .card-body
          h4.card-title.text-center
            a.btn.btn-light.btn-lg.btn-block(:href="project.address", v-if="project.address.length > 0") {{project.name}}
            div.btn.btn-light.btn-lg.btn-block(:href="project.address", v-else) {{project.name}}
            div(v-if="project.quote") 
              | "{{project.quote}}"
          p.card-text {{project.about}}
</template>
<script>
export default {
  data() {
    return {
      projects: [
        // {
        //   name: "OIIKA",
        //   quote: "Learn Something New",
        //   address: "https://oiika.com/",
        //   image: "https://www.oiika.com/735ac137a8ba71dd2b212ec2da24fab7.svg",
        //   about: "Oiika is a platform where passionate tutors and mentors share their knowledge with individuals like yourself."
        // },
        // {
        //   name: "Git Hub Repo",
        //   address: "https://github.com/derekjj",
        //   image: "https://assets-cdn.github.com/images/modules/open_graph/github-mark.png",
        //   about: "Repo of some of my college work. Mainframe Dev, Web Dev and Moblie Dev.",
        // },
        {
          name: "Who's Jimmy",
          address: "http://whosjimmy.com/",
          image: "http://whosjimmy.com/img/JIMMY_CLAWS.jpg",
          about: "Personal Portfolio of a Skilled Film Machinist, website has been reconstructed, deploy pending client approval."
        },
        {
          name: "TBD",
          address: "../projects/communication",
          image: "/taptalk.png",
          about: "Communication App(iOS, Andriod, and UWP), Designed for non-verbal or limited verbal people.",
        },
      ]
    }
  }
}
</script>

