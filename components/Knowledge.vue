<template lang="pug">
  .container
    .row
      .card
        .card-header
          h4 Knowledge
        .card-body
          .row.mb-2
            .col-12.pb-3(v-for="skill in skills")
              .row
                .col.text-left
                  h5.card-title
                    | {{skill.category}}
              .row
                .col-lg-3.col-md-4.col-sm-4(v-for="subSkill in skill.subSkills")
                  | {{subSkill}}
</template>

<script>
export default {
  data() {
    return {
      skills: [
        {
          category: "Languages",
          subSkills: [
            "HTML5",
            "ASP",
            "C++",
            "C#",
            "COBOL",
            "Html",
            "Java",
            "PHP",
            "Visual Basic",
            "Python",
            "PowerShell",
            "Java Script",
            "ReactJS",
            "NodeJS"
          ]
        },
        {
          category: "Databases",
          subSkills: ["SQLite", "Mongo", "SQLServer", "MySQLi", "PostgreSQL"]
        },
        {
          category: "Testing",
          subSkills: ["Pester", "Gatling", "Cypress", "Scout", "Sentry"]
        },
        {
          category: "Frameworks",
          subSkills: [
            "NuxtJS",
            "VueJS",
            "Laravel",
            "Ruby on Rails",
            "Spring",
            "Flutter"
          ]
        },
        {
          category: "API Integration",
          subSkills: ["Google", "Facebook", "Twitter", "Twitch", "WoW"]
        },
        {
          category: "OS",
          subSkills: ["Dos", "Unix", "Mac", "Windows", "Ubuntu"]
        },
        {
          category: "Windows 365",
          subSkills: [
            "Project",
            "Access",
            "Word",
            "Excel",
            "FrontPage",
            "PowerPoint",
            "VISIO"
          ]
        },
        {
          category: "Other",
          subSkills: [
            "Dreamweaver",
            "PHPmyAdmin",
            "AndrioStudio",
            "Xamarin",
            "JIRA",
            "Docker"
          ]
        }
      ]
    };
  },
  head() {
    return {
      titleTemplate: "Contact: %s"
    };
  }
};
</script>

<style scoped>
.card {
  margin-top: 10px;
}

.p {
  text-indent: 2em;
}
</style>


