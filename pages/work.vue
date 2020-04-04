<template lang="pug">
  .container-fluid
    .card
      .card-header
        .float-md-left
          H3 Software Developer, Phoenix Quality
        .float-md-right
          b April 2018 - Sept 2019
      .card-body
        b E-Data Now!
        br
        | Worked as a Software Developer on this near real time data collection system.  The primary use case is inspection and auditing in the automotive industry.   Typical a user will perform audits using E-Data Now Client (iOS/Swift/C++) and enter their Time sheet’s using E-  Data Now Time (Flutter/Dart).  The data is pushed up to a Rails API, where it’s presented to the Web Administrators using a cutting edge Nuxt/Vue.js frontend stack.
        br
        br
        | I had the opportunity to write code for the frontend, and backend while assisting with mobile bug fixes.  Beyond my developer duties, I maintained test plans and test cases for the entire continuum of E-Data Now products.  While performing testing duties,  I was also mandated to write automated and load tests.
        br
        br
        b Technologies Used: 
        i Postman, Mac OS, Sentry, Ruby on Rails, Scout, Jira, MS Word, MS Excel, Bootstrap, Yarn, Git, CSS, SCSS, HTML

      .card-header
        | Internship
      .card-body
        | During a one-month internship I completed Ruby on Rails, Vue.js, and clean code tutorials. Skillfully demonstrated knowledge by improving dashboard functionality by adding rearrangeable / drag and drop capabilities.
        br
        br
        b Technologies Used: 
        i Ruby on Rails, Vue.js, Nuxt.js, Bootstrap
      
      .card-header
        | S3 Bucket Processing Script
      .card-body
        | Improved PowerShell CSV script to include identifiable errors and added Pester unit tests to ensure functionality.  Conducted teleconference   meeting with overseas customer to inform them of the improvement,  and to ensure customer satisfaction.
        br
        br
        b Technologies Used: 
        i SQL Server, PowerShell, Pester, Windows

      .card-header
        | Web
      .card-body
        | In order to meet Canadian accessibility standards, I enhanced accessibility, and developed Cypress tests to verify the requirements were being met. Created Gatling scripts to generate heavy real-world load in order to observe bottlenecks in performance. Lead a   blitz to improve application performance averages.  Regularly identified slowest API calls using Scout APM.  Optimized slowest API calls by adding indexes, reducing n+1 call’s, and migrating to faster serializers.
        br
        br
        b Technologies Used: 
        i Cypress, PostgreSQL, Gatling, Nuxt.js, Vue.js, JavaScript, Scout

      .card-header
        | iOS
      .card-body
        | Was instrumental in identifying redundant and duplicate function calls causing unintended behavior. 
        br
        br
        b Technologies Used: 
        i Swift, Ruby on Rails

      .card-header
        | Cross Platform
      .card-body
        | Helped identify bugs in the code base after gaining experience on a personal Flutter application.
        br
        br
        b Technologies Used: 
        i Flutter(Dart), Ruby on Rails
      
      
      //- div  
      //-   | I was Employed until mid-September 2019, working on Mobile and Web Development at 
      //-   a(href="http://www.edatanow.com/") E-Data Now! 
      //-   | (Swift / Flutter / Nuxt.js / Vue.js / Cypress / Ruby on Rails / PowerShell / Pester / PostgreSQL & JIRA)
      //-   br
      //-   //- TODO: Add Oiika
      //-   | 
      //-   br
      //-   | Currently developing side projects with Nuxt.js / Vue.js / Flutter / Ruby on Rails & PHP
      //-   br
      //-   | The next subject I am looking to do research with is Docker.
      //-   br
      //-   b Seeking employment opportunities in Toronto to Durham and surrounding areas. With a healthy work/life balance and learning resources.
      //-   br
      //-   br
    br
    .card
      .card-header
        .float-md-left
          H3 Software Developer, Oiika
        .float-md-right
          b May 2017 –  March 2019
      .card-body
        b Oiika
        br
        | A platform where passionate tutors and mentors share their knowledge with individuals like yourself.
      .card-header
        | Web
      .card-body
        | Worked as part of the development team developing, utilizing google maps for visual displays of service areas and stripe to handle transactions.
        br
        br
        b Technologies Used: 
        i Node.js, React.js, MongoDB, Stripe, Google Maps API
      .card-header
        | Mobile
      .card-body
        | Worked pairing to develop a mirror mobile application.
        br
        br
        b Technology Used: 
        i React Native
    div
      a(href="/DerekJohnstonNoCell.pdf") Resume
</template>
<script>
export default {
  head() {
    return {
      titleTemplate: "%s"
    };
  }
};
</script>
<style scoped>
.me {
  width: 800px;
  height: 750px;
  background-image: url("~assets/me.png");
  border-radius: 50%;
}
</style>

