<template lang="pug">
  .container
    .card.my-2
      .card-header.bg-success
        H1 Various projects from Mintbean - Hackathons
      .card-body
        .row
          .col-12
            p Roles: Hackathon Lead & Participant
            p Focusing on group success over personal
            p Coding sessions are ~135mins
        .row
          .col-4.pb-2(v-for="(hackathon, index) in hackathons")
            .card.h-100
              .card-header
                h5 {{hackathon.name}}
              .card-body.h-100
                nuxt-link(:to="'MintbeanHackathons/'+ hackathon.component" v-if="hackathon.component")
                  button.m-2.btn.btn-outline-success View Demo
                a(:href="hackathon.git")
                  button.m-2.btn.btn-outline-success Github
                br
                | Objective:
                br
                | {{hackathon.objective}}
              .card-footer.pt-1.mt-1
                | {{hackathon.date}}
</template>
<script>
//TODO: Remove demos, host only with demo link from hackathons or iframe
//TODO: Update projects completed
export default {
  data() {
    return {
      dynamicComponent: "LiveCSSEditor",
      hackathons: [
        {
          name: "Markdown-Editor",
          git: "https://github.com/derekjj/2020-04-11-Markdown-Editor",
          component: "MarkdownEditor",
          date: "2020-04-11",
          objective: "create your own Markdown Editor."
        },
        {
          name: "Roll-Your-Own-Chrome-Dashboard",
          git:
            "https://github.com/derekjj/2020-04-08-Roll-your-own-Chrome-dashboard",
          date: "2020-04-08",
          objective: "create your own dashboard for Chrome."
        },
        {
          name: "Live-CSS-Editor",
          git: "https://github.com/derekjj/2020-04-04-Live-CSS-Editor",
          component: "LiveCSSEditor",
          date: "2020-04-04",
          objective: "create an in-site CSS editor of your own design."
        },
        {
          name: "Interactive-Calculator",
          git: "https://github.com/derekjj/2020-04-01-Interactive-Calculator",
          component: "InteractiveCalculator",
          date: "2020-04-01",
          objective:
            "create a simple interactive calculator of your own design."
        },
        {
          name: "HackTheResume",
          component: "HackTheResume",
          git: "https://github.com/derekjj/2020-03-28-HackTheResume",
          date: "2020-03-28",
          objective:
            "create a simple resume builder form that saves resume information inside a JSON Resume object."
        },
        {
          name: "ResumeBuilder",
          component: "ResumeBuilder",
          git: "https://github.com/derekjj/ResumeBuilder",
          date: "2020-03-21",
          objective:
            "build a project where we take JSON Resume object as an input. Using this JSON object, we will output a fully-formatted resume page. Recieved 3rd place."
        },
        {
          name: "HackTheResume",
          git: "https://github.com/derekjj/HackTheResume",
          date: "2020-03-14",
          objective:
            "build template(s) for resumes to display data recevied from a json object."
        }
      ]
    };
  }
};
</script>