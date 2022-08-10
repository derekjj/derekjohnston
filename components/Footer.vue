<template lang="pug">
footer.d-flex.justify-content-around.social-footer.bg-success
  b-row.social-footer-icons 
    //- a.col-sm-3(href="https://www.facebook.com/DJDesign.ca")
      i.fa.fa-facebook(aria-hidden="true")
    b-col
      a.text-white(href="https://github.com/derekjj")
        i.fa.fa-github(aria-hidden="true")
    b-col
      a.text-white(href="https://gitlab.com/derekjj")
        i.fa.fa-gitlab(aria-hidden="true")
    b-col
      a.text-white(href="https://www.linkedin.com/in/derekjjohnston")
        i.fa.fa-linkedin(aria-hidden="true")
    b-col
      router-link.text-white(to="/contact")
        i.fa.fa-address-card-o(aria-hidden="true")
</template>
<style scoped>
a.text-white {
  text-shadow: #222 0.1em 0.1em 0.1em;
}
.social-footer {
  padding: 1rem;
}

.social-footer .social-footer-icons .fa {
  font-size: 1.6rem;
  color: #fefefe;
}

.social-footer .social-footer-icons .fa:hover {
  color: #4a4a4a;
  transition: color 0.3s ease-in;
}
</style>