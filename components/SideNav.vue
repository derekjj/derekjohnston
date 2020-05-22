<template lang="pug"> 
  .px-3.py-2.text-center
    .row
      .col
        nuxt-link(to="/")
          b-img.rounded-circle(src="~assets/me2.jpg" alt="Derek Johnston" fluid thumbnail)
    .row
      .col
        nuxt-link(to="/")
          h1 Derek Johnston
        .list-group
          b-button.m-1(variant="success"
                      activeClass="active",
                      to="/knowledge") Knowledge

          b-button.m-1(variant="success"
                      activeClass="active",
                      to="/projects") Projects

          b-button.m-1(variant="success"
                      activeClass="active",
                      to="/contact") Contact
    .row
      .col
        a.text-white.col-sm-3(href="https://github.com/derekjj")
          i.fa.fa-github(aria-hidden="true")
        a.text-white.col-sm-3(href="https://gitlab.com/derekjj")
          i.fa.fa-gitlab(aria-hidden="true")
        a.text-white.col-sm-3(href="https://www.linkedin.com/in/derekjjohnston")
          i.fa.fa-linkedin(aria-hidden="true")
        router-link.text-white.col-sm-3(to="/contact")
          i.fa.fa-address-card-o(aria-hidden="true")
</template>
<style scoped>
a.text-white{
  text-shadow: #222 0.1em 0.1em 0.1em;
}
</style>