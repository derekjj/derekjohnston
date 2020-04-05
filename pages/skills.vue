<template lang="pug">
  .container
    .row
      .col-lg-3.mb-3(v-for="skill in skills")
        .card.h-100
          .card-header.text-center
            h4.card-title
              | {{skill.category}}
          .card-body
            ul.list-group.list-group-flush
              li.list-group-item(v-for="subSkill in skill.subSkills")
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
            "Java Script",
            "MySQLi",
            "PHP",
            "SQL",
            "Visual Basic",
            "Python",
            "PowerShell",
            "Pester",
            "Gatling",
            "Cypress",
            "React"
          ]
        },
        {
          category: "Frameworks",
          subSkills: [
            "NuxtJS",
            "VueJS",
            "NodeJS",
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
          category: "Other",
          subSkills: [
            "Project",
            "Access",
            "Word",
            "Excel",
            "FrontPage",
            "PowerPoint",
            "VISIO",
            "Dos / Unix",
            "Windows 3.1 to 10",
            "Dreamweaver",
            "PHPmyAdmin",
            "AndrioStudio",
            "Xamarin",
            "MacOS",
            "JIRA",
            "Scout",
            "PostgreSQL",
            "SQL Server",
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


