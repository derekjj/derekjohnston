<template lang="pug">
div
    .row.bg-success
      .col
        H1 Projects
    .row
      .col-sm-6.col-lg-4.my-3(v-for="project in projects")
        .card
          .card-header.m-1
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
          name: "Admin Web Service",
          address: "https://service.edatanow.com",
          image: "https://media-exp1.licdn.com/dms/image/C4D0BAQGKWsYf3h1Brg/company-logo_200_200/0?e=1597881600&v=beta&t=xCDbYKHX1utCfufYIgnG1Cd3EaSAXBXZrsxnM9Wn1ac",
          about:
            "Administrative portal for supporting mobile apps."
        },
        {
          name: "Audit & Inspection",
          address: "https://apps.apple.com/ca/app/edatanow/id633948920",
          image: "https://media-exp1.licdn.com/dms/image/C4D0BAQGKWsYf3h1Brg/company-logo_200_200/0?e=1597881600&v=beta&t=xCDbYKHX1utCfufYIgnG1Cd3EaSAXBXZrsxnM9Wn1ac",
          about:
            "Mobile app in Swift for iOS devices."
        },
        {
          name: "Timesheets App",
          address: "https://apps.apple.com/ca/app/edn-time/id1471165421",
          image: "https://media-exp1.licdn.com/dms/image/C4D0BAQGKWsYf3h1Brg/company-logo_200_200/0?e=1597881600&v=beta&t=xCDbYKHX1utCfufYIgnG1Cd3EaSAXBXZrsxnM9Wn1ac",
          about:
            "Mobile app in Flutter for all mobile devices."
        },
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