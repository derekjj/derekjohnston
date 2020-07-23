<template lang="pug">
.container-flex.mt-5
  .row.bg-success
    .col-12
      H1 Mintbean Hackathon's 
  .row
    .col-12
      sub * code time: ~2hrs to ~4hrs *
  .row.mx-5.my-2
    .col-12
      b-form-select(v-model="selected" :options="options")
  .row(v-if="demo")
    .col-12.m-2
      b-button(:href="git" variant="info") Code Repo
      b-button(:href="demo" variant="success") Demo
    .col-12.vh-iframe
      iframe.h-100(:src="demo" )
  .row(v-if="selected && !demo")
    .col-12.m-2
      b-button(:href="git" variant="info") Code Repo
    .col-12 No Demo for this project
  .row(v-if="!selected")
    .col-12 Please select a hackathon
</template>
<script>
export default {
  layout: "demo",
  mounted() {
    this.selected = parseInt(this.$route.query.project);
    if (!this.selected) this.selected = this.options.length;
  },
  data() {
    return {
      selected: null,
      options: [
        {
          git: "https://github.com/derekjj/colour-picker-mintbean-hackathon",
          text: "2020-07-22 - colour-picker",
          demo: "https://colour-picker-mintbean-hackathon.derekjj.vercel.app/",
          value: 23
        },
        {
          git: "https://github.com/derekjj/2020-07-13-bulma-theme",
          text: "2020-07-13 - bulma-theme",
          demo: "https://2020-07-13-bulma-theme.derekjj.vercel.app/",
          value: 22
        },
        {
          git: "https://github.com/derekjj/2020-07-08-hack-exchange",
          text: "2020-07-08 - hack-exchange",
          demo:
            "https://2020-07-08-hack-exchange-git-master.derekjj.vercel.app/",
          value: 21
        },
        {
          git: "https://github.com/derekjj/2020-05-27-meme-maker",
          text: "2020-05-27 - meme-maker",
          demo: "https://2020-05-27-meme-maker.now.sh/",
          value: 20
        },
        {
          git: "https://github.com/derekjj/2020-05-20-tell-your-story-in-data",
          text: "2020-05-20 - tell-your-story-in-data",
          demo: "https://2020-05-20-tell-your-story-in-data.now.sh/",
          value: 19
        },
        {
          git: "https://github.com/derekjj/2020-05-18-hack-the-resume",
          text: "2020-05-18 - hack-the-resume",
          demo: "https://2020-05-18-hack-the-resume.now.sh/",
          value: 18
        },
        {
          git: "https://github.com/derekjj/2020-05-13-markdown-editor",
          text: "2020-05-13 - markdown-editor",
          demo: "https://2020-05-13-markdown-editor.now.sh/",
          value: 17
        },
        {
          git: "https://github.com/derekjj/2020-05-11-noisemaker",
          text: "2020-05-11 - noisemaker",
          demo: "https://2020-05-11-noisemaker.now.sh/",
          value: 16
        },
        {
          git: "https://github.com/derekjj/2020-05-06-Job-Application-Tracker",
          text: "2020-05-06 - Job-Application-Tracker",
          demo: "https://2020-05-06-job-application-tracker-gules.now.sh/",
          value: 15
        },
        {
          git: "https://github.com/derekjj/2020-05-04-Interactive-Calculator",
          text: "2020-05-04 - Interactive-Calculator",
          demo: "https://2020-05-04-interactive-calculator.derekjj.now.sh/",
          value: 14
        },
        {
          git: "https://github.com/derekjj/2020-04-29-script-runner",
          text: "2020-04-29 - script-runner",
          demo: "",
          value: 13
        },
        {
          git: "https://github.com/derekjj/2020-04-24-meme-maker",
          text: "2020-04-24 - meme-maker",
          demo: "https://2020-04-24-meme-maker.derekjj.now.sh/",
          value: 12
        },
        {
          git: "https://github.com/derekjj/2020-04-22-Noisemaker",
          text: "2020-04-22 - Noisemaker",
          demo: "https://2020-04-22-noisemaker-phi.now.sh/",
          value: 11
        },
        {
          git:
            "https://github.com/derekjj/2020-04-19-Conways-Game-of-Life-4-day-extended",
          text: "2020-04-19 - Conways-Game-of-Life-4-day-extended",
          demo:
            "https://2020-04-19-conways-game-of-life-4-day-extended-three.now.sh/",
          value: 10
        },
        {
          git: "https://github.com/derekjj/2020-04-17-personal-npm-package",
          text: "2020-04-17 - personal-npm-package",
          demo: "",
          value: 9
        },
        {
          git: "https://github.com/derekjj/2020-04-15-Conways-Game-of-Life",
          text: "2020-04-15 - Conways-Game-of-Life",
          demo: "https://2020-04-15-conways-game-of-life.now.sh/",
          value: 8
        },
        {
          git: "https://github.com/derekjj/2020-04-11-Markdown-Editor",
          text: "2020-04-11 - Markdown-Editor",
          demo: "https://2020-04-11-markdown-editor.derekjj.now.sh/",
          value: 7
        },
        {
          git:
            "https://github.com/derekjj/2020-04-08-Roll-your-own-Chrome-dashboard",
          text: "2020-04-08 - Roll-your-own-Chrome-dashboard",
          demo: "",
          value: 6
        },
        {
          git: "https://github.com/derekjj/2020-04-04-Live-CSS-Editor",
          text: "2020-04-04 - Live-CSS-Editor",
          demo: "",
          value: 5
        },
        {
          git: "https://github.com/derekjj/2020-04-01-Interactive-Calculator",
          text: "2020-04-01 - Interactive-Calculator",
          demo: "https://2020-04-01-interactive-calculator-lovat.now.sh/",
          value: 4
        },
        {
          git: "https://github.com/derekjj/2020-03-28-HackTheResume",
          text: "2020-03-28 - HackTheResume",
          demo: "https://2020-03-28-hack-the-resume.now.sh/",
          value: 3
        },
        {
          git: "https://github.com/derekjj/ResumeBuilder",
          text: "2020-03-21 - ResumeBuilder",
          demo: "",
          value: 2
        },
        {
          git: "https://github.com/derekjj/HackTheResume",
          text: "2020-03-14 - HackTheResume",
          demo: "",
          value: 1
        }
      ]
    };
  },
  computed: {
    git() {
      return this.options.find(e => e.value === this.selected).git;
    },
    demo() {
      if (this.options.find(e => e.value === this.selected) != undefined) {
        return this.options.find(e => e.value === this.selected).demo;
      } else {
        return false;
      }
    }
  }
};
</script>
<style scoped>
.vh-iframe {
  height: 69vh;
}
iframe {
  width: 100%;
  height: 500px;
}
</style>