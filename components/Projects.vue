<template lang="pug">
  .card.my-2
    .card-header.bg-success
      H1 Projects
    .card-body
      .row
        .col-md-4.my-3(v-for="project in projects")
          .card.h-100
            .card-header.m-1.h-100
              router-link(:to="project.address", v-if="project.local && project.address.length > 0")
                img.card-img-top(:src="project.image")
              a(:href="project.address", v-if="!project.local && project.address.length > 0")
                img.card-img-top(:src="project.image")
              div(v-if="project.address.length <= 0")
                img.card-img-top(:src="project.image")
            .card-body.mb-3
              h5.text-center
                a.btn.btn-light.btn-lg.btn-block(:href="project.address", v-if="project.address.length > 0") {{project.name}}
                div.btn.btn-light.btn-lg.btn-block(:href="project.address", v-else) {{project.name}}
                div(v-if="project.quote") 
                  | "{{project.quote}}"
            .card-footer
              p.card-text {{project.about}}
</template>
<script>
export default {
  data() {
    return {
      projects: [
        {
          name: "Mintbean Hackathons",
          address: "./projects/MintbeanHackathons",
          local: true,
          image: "https://avatars2.githubusercontent.com/u/41805626?s=200&v=4",
          about:
            "Examples of Hackathon projects."
        },
        {
          name: "Who's Jimmy",
          address: "http://whosjimmy.com/",
          image: "http://whosjimmy.com/img/JIMMY_CLAWS.jpg",
          about:
            "Personal Portfolio of a Skilled Film Machinist, website has been reconstructed, deploy pending client approval."
        },
        {
          name: "TBD",
          address: "./projects/communication",
          local: true,
          image: "/taptalk.png",
          about:
            "Communication App(iOS, Andriod, and UWP), Designed for non-verbal or limited verbal people."
        }
      ]
    };
  }
};
</script>

<style scoped>
.card-header {
  background-color: #fff;
}
</style>