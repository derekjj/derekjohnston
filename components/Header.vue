<template lang="pug">
  b-navbar.bg-success(toggleable="sm" type="dark" fixed="top")
    b-button.d-none.d-sm-block.mr-2(v-b-toggle.sidebar-variant variant="success")
      .navbar-toggler-icon

    b-navbar-toggle.d-sm-none(target="nav-collapse")
    b-collapse(id="nav-collapse" is-nav)
      b-navbar-nav.ml-auto.d-sm-none
        b-nav-item(tag="b-button",
                  activeClass="active",
                  to="/"
                  exact) Home
        b-nav-item(tag="b-button",
                  activeClass="active",
                  to="/knowledge") Knowledge
        b-nav-item(tag="b-button",
                  activeClass="active",
                  to="/projects") Projects
        b-nav-item(tag="b-button",
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