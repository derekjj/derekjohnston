<template lang="pug">
  .container
    .row
      .col-sm-6.mb-3(v-for="skill in skills")
        .card.h-100
          .card-header.text-center
            h4.card-title
              | {{skill.category}}
          .card-body
            ul.list-group.list-group-flush
              li.list-group-item(v-for="subSkill in skill.subSkills")
                | {{subSkill}}
    .card
      .card-body
        | There are additional skills, this is just a small list to show interest in learning.
        br
        br
        | Some additional interests I have are camping, swimming, biking, fishing, and hunting. The elective classes I took are Human Resources I & II, Accounting I, Children’s Literature, and Find Your Fit (Fitness). I like to work locally or remotely but will move for the right job. Current Located in Durham Ontario, Canada.
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
          category: "Software",
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
            "SQL Server"
          ]
        },
        {
          category: "Frameworks",
          subSkills: [
            "NodeJS",
            "VueJS",
            "Laravel",
            "Ruby on Rails",
            "Spring",
            "Flutter"
          ]
        },
        {
          category: "Integration",
          subSkills: ["Google", "Facebook", "Twitter", "Twitch.tv", "WoW"]
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


