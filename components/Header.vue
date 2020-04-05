<template lang="pug">
  div
    b-navbar(toggleable="sm" type="dark" variant="success" fixed="top")
      
      b-navbar-brand.d-none.d-sm-block(to="/") Derek Johnston
      b-navbar-brand.d-sm-none(to="/") Derek Johnston

      b-navbar-toggle(target="nav-collapse")

      b-collapse(id="nav-collapse" is-nav)
        b-navbar-nav.ml-auto
          //- b-nav-item(to="/about",
          //-           activeClass="active") About
          b-nav-item(tag="button",
                    activeClass="active",
                    to="/skills") Skills
          //- b-nav-item(tag="button",
                    activeClass="active",
                    to="/work") Work Exp
          b-nav-item(tag="button",
                    activeClass="active",
                    to="/projects") Projects
          b-nav-item(tag="button",
                    activeClass="active",
                    to="/contact") Contact
</template>

<style scoped>
.dropdown-menu {
  background-color: #28a745 !important;
}
.hoverable:hover {
  -webkit-box-shadow: none;
  box-shadow: 0px 2px 2px 2px #cccccc;
  -webkit-transition: all 0.8s ease-in-out;
  transition: all 0.8s ease-in-out;
}
</style>