<template lang="pug">
  .container
    .row
      .col-12
        H2 Various projects from Mintbean - Hackathons
    .row
      .col-12
        p Roles: Hackathon Lead & Participant
        p Coding sessions are ~135mins
    .row(v-if="show")
      .col-4.pb-2(v-for="(hackathon, index) in hackathons")
        .card.h-100
          .card-header
            h5 {{hackathon.name}}
          .card-body.h-100
            button.m-2.btn.btn-outline-success(@click="toggleComponent(hackathon.component)" v-if="hackathon.component") View Demo
            button.m-2.btn.btn-outline-success(:href="hackathon.git") Github
            br
            | Objective:
            br
            | {{hackathon.objective}}
          .card-footer.pt-1.mt-1
            | {{hackathon.date}}
    .row(v-else)
      button.m-2.btn.btn-outline-success(@click="show = !show") Back      
      component(:is="dynamicComponent")
</template>
<script>
import LiveCSSEditor from '~/components/MintbeanHackathons/LiveCSSEditor.vue'
import InteractiveCalculator from '~/components/MintbeanHackathons/InteractiveCalculator.vue'
import HackTheResume from '~/components/MintbeanHackathons/HackTheResume.vue'
import ResumeBuilder from '~/components/MintbeanHackathons/ResumeBuilder.vue'
export default {
  components: {
    LiveCSSEditor,
    InteractiveCalculator,
    HackTheResume,
    ResumeBuilder
  },
  methods: {
    toggleComponent(component) {
      this.show = false
      this.dynamicComponent=component
    }
  },
  data() {
    return {
      show:true,
      dynamicComponent: 'LiveCSSEditor',
      hackathons: [
        {
          name: "HackTheResume",
          git: "https://github.com/derekjj/HackTheResume",
          date: "2020-03-14",
          objective:
            "build template(s) for resumes to display data recevied from a json object."
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
          component: "HackTheResume",
          git: "https://github.com/derekjj/2020-03-28-HackTheResume",
          date: "2020-03-28",
          objective:
            "create a simple resume builder form that saves resume information inside a JSON Resume object."
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
          name: "Live-CSS-Editor",
          git: "https://github.com/derekjj/2020-04-04-Live-CSS-Editor",
          component: "LiveCSSEditor",
          date: "2020-04-04",
          objective: "create an in-site CSS editor of your own design."
        }
      ]
    };
  }
};
</script>