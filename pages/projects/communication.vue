<template lang="pug">
  .container-fluid
    .card
      .card-header
        | Communication App (Under Construction) 
      .card-body
        .card-title
          H5 Inspiration: my son who is in need of a Communication aid.
          br
          | This was started as my third year project in Xamarin but with the new knowledge of flutter I have decided to remake it.  In order to reinforce knowledge gained.
          br
          br
          ul
            li The app will consist of a gird of buttons that a user can use to either play a recorded voice messages or play text to speech.
            li The app will be highly customizable for accessibly! (colours/size/vibration/screen-lock/etc.)
          br
          H5 The Plan
          ul
            li To release on the Google Play Store then Apple Store.
            li Focus on tablet then phones (I know this is backward development, but tablets are the more common communication aid.)
          br
          H5 Future ideas
          ul
            li Pro-Version with accounts and remote syncing.
            li Categories with easy to enable and disable.
              br
              | ex. @Home but its raining, turn off "outside" category.

    br
</template>
<script>
export default {
  head() {
    return {
      titleTemplate: '%s'
    }
  }
}
</script>
<style scoped>
.me {
  width: 800px;
  height: 750px;
  background-image: url('~assets/me.png');
  border-radius: 50%;
}
</style>

