<template lang="pug">
.container-fluid.pt-4
  .row
    .col-7.align-self-center.text-start
      H2 {{ profile.name.first }} {{ profile.name.last }}
    .col-5.text-end
      div(v-if="profile.phone") {{ profile.phone }}
      div(v-for="link in profile.links")
        .row 
          a(:href="link.url") {{ link.text }}
  .row
    .col.text-start.fw-bold.text-decoration-underline Development Experience
  template(v-for="exp in experience")
    .row
      .col-8.fw-bold.text-start
        template(v-if="exp.title") {{ exp.title }}, {{ exp.company }}
        template(v-else) {{ exp.company }}
      .col-4.fw-bold.text-end {{ exp.date.start }} - {{ exp.date.end }}
    .row
      .col-3.text-start.text-decoration-underline Technologies
      .col-9.text-start.text-wrap
        template(v-for="(tech, i) in exp.technologies")
          template(v-if="i !== exp.technologies.length - 1") {{ `${tech}, ` }}
          template(v-else) and {{ tech }}.
    .row
      .col-3.text-start.text-decoration-underline Projects
      .col-9.text-start.text-decoration-underline Description
    .row(v-for="project in exp.projects")
      .col-3.text-start {{ project.name }}
      .col-9.text-start
        p(v-for="description in project.descriptions") {{ description }}
  .row
    .col.text-start.fw-bold.text-decoration-underline Education
  template(v-for="exp in education")
    .row
      .col-8.fw-bold.text-start
        template(v-if="exp.title") {{ exp.title }}, {{ exp.company }}
        template(v-else) {{ exp.company }}
      .col-4.fw-bold.text-end
        template(v-if="exp.date.start") {{ exp.date.start }} -&nbsp;
        template {{ exp.date.end }}
    .row
      .col-3.text-start.text-decoration-underline Technologies
      .col-9.text-start.text-wrap
        template(v-for="(tech, i) in exp.technologies")
          template(v-if="i !== exp.technologies.length - 1") {{ `${tech}, ` }}
          template(v-else) and {{ tech }}.
    .row
      .col-3.text-start.text-decoration-underline Projects
      .col-9.text-start.text-decoration-underline Description
    .row(v-for="project in exp.projects")
      .col-3.text-start {{ project.name }}
      .col-9.text-start
        p(v-for="description in project.descriptions") {{ description }}
</template>
<script>
export default {
  layout: "demo",
  data() {
    return {
      profile: {
        name: { first: "Derek", last: "Johnston" },
        phone: "905.926.8279",
        links: [
          {
            text: "derek@derekjohnston.ca",
            url: "mailto:derek@derekjohnston.ca",
          },
          {
            text: "https://derekjohnston.ca",
            url: "https://derekjohnston.ca",
          },
          {
            text: "https://github.com/derekjj",
            url: "https://github.com/derekjj",
          },
          {
            text: "https://gitlab.com/derekjj",
            url: "https://gitlab.com/derekjj",
          },
          {
            text: "https://www.linkedin.com/in/derekjjohnston",
            url: "https://www.linkedin.com/in/derekjjohnston",
          },
        ],
      },
      experience: [
        {
          title: "Lead Full Stack Developer",
          company: "Youville Haussmann Park",
          date: {
            start: "May 2021",
            end: "Present ",
          },
          technologies: [
            "GatsbyJS",
            "NextJS",
            "ReactJS",
            "TypeScript",
            "JavaScript",
            "WordPress",
            "Symfony",
            "PhP",
            "Docker",
            "AWS",
            "ClickUp",
            "TeamWork",
            "Bitbucket",
            "Playfab",
            "SaSS",
          ],
          projects: [
            {
              name: "Communication Aid",
              descriptions: [
                "YHP is an experience agency. Not just experiential, and not just branded events. YHP specializes in tapping into human experiences to create lasting brand engagement for its clients. YHP works with brands to plan, execute and capture emotional and memorable moments. Through impossibly on-point experiential campaigns and industry best practices, YHP is strengthening relationships between brands and their customers. Armed with a deep understanding of the emerging arts, culture and the need to share human experiences, YHP builds unique brand experiences and engagement strategies to engage with the mindset and motivations of real people.",
              ],
            },
            {
              name: "Overview",
              descriptions: [
                "YHP is an experience agency. Not just experiential, and not just branded events. YHP specializes in tapping into human experiences to create lasting brand engagement for its clients. YHP works with brands to plan, execute and capture emotional and memorable moments. Through impossibly on-point experiential campaigns and industry best practices, YHP is strengthening relationships between brands and their customers. Armed with a deep understanding of the emerging arts, culture and the need to share human experiences, YHP builds unique brand experiences and engagement strategies to engage with the mindset and motivations of real people.",
              ],
              name: "Role",
              descriptions: [
                "- Constantly improving the code base.",
                "- Deciding if development is possible or not while giving possible alternatives.",
                "- Assisting with consultation and troubleshooting of technical problems.",
                "- Helping provide estimations of work.",
                "- Coaching",
                "- Working on multiple projects at the same time.",
                "- Merging and Deploying projects.",
                "- Upgrading library dependancies.",
              ],
            },
          ]
        },
        {
          title: "",
          company: "Johnston Software Development",
          date: {
            start: "Jan 2020",
            end: "current",
          },
          technologies: [
            "Postman",
            "Jira",
            "Bootstrap",
            "Tailwind",
            "Yarn",
            "Git",
            "CSS",
            "SCSS",
            "SQLite",
            "RoomDB",
            "PHP",
            "NuxtJS",
            "VueJS",
            "ReactJS",
            "NodeJS",
            "JavaScript",
            "Swift",
            "Java",
            "Flutter (Dart)",
          ],
          projects: [
            {
              name: "Communication Aid",
              descriptions: [
                "Ongoing development of a Flutter communication application in order to assist verbally limited individuals, family, friends and assist support professionals.",
              ],
            },
            {
              name: "Zero Projects",
              descriptions: [
                "Developed a shipping JAVA ANDROID application in order to replace an existing Cordova app. Utilizing Postman, Git, and RoomDB. ",
              ],
            },
            {
              name: "Tackle Hunger",
              descriptions: [
                "Developed a map component in order to display food banks and their needs across North America. Utilizing Yarn, Tailwind, Git, ReactJS, and Algolia(utilizes google Map).",
              ],
            },
            {
              name: "Who’s Jimmy",
              descriptions: [
                "Ongoing development of a professional portfolio for a skilled film craftsman and clock-smith. Utilizing VueJS/NuxtJS and PHP.",
              ],
            },
          ],
        },
        {
          title: "Software Developer",
          company: "Phoenix Quality",
          date: {
            start: "May 2018",
            end: "Sept 2019",
          },
          technologies: [
            "Postman",
            "Sentry",
            "Ruby on Rails",
            "Scout",
            "Jira",
            "Bootstrap",
            "Yarn",
            "Git",
            "CSS",
            "SCSS",
            "HTML",
            "SQL Server",
            "PowerShell",
            "Pester",
            "Cypress",
            "PostgreSQL",
            "Gatling",
            "NuxtJS",
            "VueJS",
            "JavaScript",
            "Scout",
            "Swift",
            "Flutter (Dart)",
          ],
          projects: [
            {
              name: "Overview",
              descriptions: [
                "Worked as a Software Craftsman for “E-Data Now!” (EDN) product. EDN is a near real time data collection system. The primary use case is inspection and auditing in the automotive industry. Typically, a user will perform audits using EDN Client (iOS/Swift/C++) and enter their Time sheet’s using EDN Time (Flutter/Dart). The data is pushed up to a Rails API, where it is presented to the Web Administrators using a cutting edge Nuxt.js/Vue.js frontend stack.",
                "I had the opportunity to write code for the frontend, and backend while assisting with mobile bug fixes. Beyond my developer duties, I maintained test plans and test cases for the entire suite of EDN products. While performing testing duties, I was also mandated to write automated and load tests. ",
              ],
            },
            {
              name: "Internship",
              descriptions: [
                "During a one-month internship I completed Ruby on Rails, Vue.js, and clean code tutorials.",
                "Skillfully demonstrated knowledge by improving dashboard functionality by adding rearrangeable / drag and drop capabilities. ",
              ],
            },
            {
              name: "S3 Bucket Processing Script",
              descriptions: [
                "Improved PowerShell CSV script to include identifiable errors and added Pester unit tests to ensure functionality. Conducted teleconference meeting with overseas customer to inform them of the improvement, and to ensure customer satisfaction.",
              ],
            },
            {
              name: "Web",
              descriptions: [
                "In order to meet Canadian accessibility standards, I enhanced accessibility, and developed Cypress tests to verify the requirements were being met.",
                "Created Gatling scripts to generate heavy real-world load in order to observe bottlenecks in performance.",
                "Lead a blitz to improve application performance averages. Regularly identified slowest API calls using Scout APM. Optimized slowest API calls by adding indexes, reducing n+1 call’s, and migrating to faster serializers.",
              ],
            },
            {
              name: "iOS",
              descriptions: [
                "Was instrumental in identifying redundant and duplicate function calls causing unintended behavior.",
              ],
            },
            {
              name: "Cross Platform",
              descriptions: [
                "Helped identify bugs in the Flutter code base after gaining experience on a personal Flutterapplication.",
              ],
            },
          ],
        },
        {
          title: "Software Developer",
          company: "Oiika",
          date: {
            start: "May 2017",
            end: "March 2019",
          },
          technologies: [
            "NodeJS",
            "ReactJS",
            "MongoDB",
            "Stripe",
            "Google Maps API",
            "React Native",
          ],

          projects: [
            {
              name: "Web App",
              descriptions: [
                "Worked as part of the development team developing Oiika for connecting tutors to tutees, utilizing google maps for visual displays of service areas and stripe to handle transactions.",
              ],
            },
            {
              name: "Mobile App",
              descriptions: [
                "Lead the charge to develop a mirror React Native mobile application.",
              ],
            },
          ],
        },
      ],
      education: [
        {
          title: "Computer Programmer Analyst Advanced Diploma(3yr)",
          company: "Durham College",
          date: {
            end: "April 2018",
          },
          technologies: [
            "PHP",
            "ASP",
            "JAVA",
            "COBOL",
            "SQL",
            "MySQL",
            "C#",
            "C++",
            "Visual Basic",
            "VISIO",
            "Ubuntu",
            "MS Studio",
            "phpMyAdmin",
            "Android studio",
            "Visual Studio",
            "Xamarin",
            "Spring",
            "ReactJS",
            "Ruby on Rails.",
          ],

          projects: [
            {
              name: "Final Project",
              descriptions: [
                "Lead Developer for a mobile communication application using Xamarin targeting verbally limited individuals.",
              ],
            },
          ],
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
</style>