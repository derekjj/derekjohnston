<template lang="pug">
transition(name="fade")  
  .card(v-if="isShowing")
    .card-header
      .row
        .col-2
        .col-8
          h4 Knowledge
        .col-2.text-right.text-white
          b-button.m-1(variant="success" v-b-toggle.collapse-primary)
            span.when-opened
              i.fa.fa-chevron-down(aria-hidden="true")
            span.when-closed
              i.fa.fa-chevron-up(aria-hidden="chevron-right")
    .card-body
      b-collapse#collapse-primary(visible)
        .row
          .col-12.pb-3(v-for="skill in skills")
            .row
              .col.text-left
                h5.card-title
                  | {{skill.category}}
            .row
              .col-lg-3.col-md-4.col-sm-4(v-for="subSkill in skill.subSkills")
                | {{subSkill}}
    .row
      .col-12.p-0
        Secondary
</template>

<script>
import Secondary from "~/components/Knowledge/Secondary";
export default {
  components: {
    Secondary
  },
  data() {
    return {
      isShowing: false,
      skills: [
        {
          category: "JavaScript",
          subSkills: ["JavaScript", "ReactJS", "NodeJS", "NuxtJS/VueJS"]
        },
        {
          category: "Databases",
          subSkills: ["SQLite", "MongoDB", "SQLServer", "MySQLi", "PostgreSQL"]
        },
        {
          category: "Frameworks",
          subSkills: ["NuxtJS/VueJS", "Ruby on Rails", "Flutter"]
        },
        {
          category: "API Integration",
          subSkills: [
            "Google",
            "Facebook",
            "Twitter",
            "Twitch",
            "WoW",
            "Github"
          ]
        }
      ]
    };
  },
  head() {
    return {
      titleTemplate: "Contact: %s"
    };
  },
  mounted() {
    this.isShowing = true;
  }
};
</script>

<style scoped>
.collapsed > .when-opened,
:not(.collapsed) > .when-closed {
  display: none;
}

.card {
  margin-top: 10px;
}

.p {
  text-indent: 2em;
}
</style>