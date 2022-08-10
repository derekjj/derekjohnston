<template lang="pug">
  .card.my-2
    .card-header.bg-success
      H1 Projects
    .card-body
      .row
        .col-sm-6.col-md-6.col-lg-4.my-1(v-for="project in projects")
          .card
            //- .card-header.h-100.m-1
            //-   router-link(:to="project.address", v-if="project.local && project.address.length > 0")
            //-     img.card-img-top(:src="project.image")
            //-   a(:href="project.address", v-if="!project.local && project.address.length > 0")
            //-     img.card-img-top(:src="project.image")
            //-   div(v-if="project.address.length <= 0")
            //-     img.card-img-top(:src="project.image")
            .card-body.pt-0
              router-link(:to="project.address", v-if="project.local && project.address.length > 0")
                h5.text-center
                  a.btn.btn-light.btn.btn-block(:href="project.address", v-if="project.address.length > 0") {{project.name}}
                  div.btn.btn-light.btn.btn-block(:href="project.address", v-else) {{project.name}}
                  div(v-if="project.quote") 
                    | "{{project.quote}}"
              a(:href="project.address", v-if="!project.local && project.address.length > 0")
                h5.text-center
                  a.btn.btn-light.btn.btn-block(:href="project.address", v-if="project.address.length > 0") {{project.name}}
                  div.btn.btn-light.btn.btn-block(:href="project.address", v-else) {{project.name}}
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
          name: "YHP",
          address: "https://youville-haussmannpark.com/",
          // local: true,
          // image: "https://avatars2.githubusercontent.com/u/41805626?s=200&v=4",
          about:
            "Lead Full Stack Developer"
        },
        {
          name: "Hackathons",
          address: "./projects/hackathons",
          local: true,
          image: "https://avatars2.githubusercontent.com/u/41805626?s=200&v=4",
          about:
            "Examples of Hackathon projects."
        },
        {
          name: "E-Data Now!",
          address: "./projects/EDataNow",
          local: true,
          image: "https://media-exp1.licdn.com/dms/image/C4D0BAQGKWsYf3h1Brg/company-logo_200_200/0?e=1597881600&v=beta&t=xCDbYKHX1utCfufYIgnG1Cd3EaSAXBXZrsxnM9Wn1ac",
          about:
            "At this Audit and Inspection company, working on a large administrative website and 2 supporting monbile apps."
        },
        {
          name: "Oiika",
          address: "https://Oiika.com",
          image: "https://media-exp1.licdn.com/dms/image/C560BAQE4SjQ4e5b-sg/company-logo_200_200/0?e=1597881600&v=beta&t=i3hWuPgeSdgVqgUBJ9rPgA9Um6ItpRyLqrq5lJAP90Q",
          about:
            "Connecting tutors and tutees!"
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