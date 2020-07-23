<template lang="pug">
  .card.my-2
    .card-header
      H1 Contact
    .card-body
      .row.m-1
        .col-lg-12
          h2 Derek Johnston
          h6
            |  Software Developer
          h6
            a(href="mailto:Derek@DerekJohnston.ca") 
              span.fa.fa-envelope(data-toggle="tooltip" title="Derek@DerekJohnston.ca")
              |  Derek@DerekJohnston.ca
      .row.m-2
        .col-lg-12.pt-2
          <form action="https://formspree.io/derek@derekjohnston.ca" method="post">
            <div class="form-group">
                <input type="text" id="name" name="name" class="form-control" placeholder="Name">
            </div>
            <div class="form-group">
                <input type="text" id="email" name="email" class="form-control" placeholder="Email">
            </div>
            <div class="form-group">
                <input type="text" id="subject" name="_subject" class="form-control" placeholder="Subject">
            </div>
            <div class="form-group">
                <textarea id="message" name="message" cols="30" rows="7" class="form-control" placeholder="Message..."></textarea>
            </div>
            <div class="form-group">
                <input type="submit" class="btn btn-primary btn-send-message" value="Send Message">
            </div>
          </form>
</template>
<script>
//TODO: add from validation
export default {
  data() {
    return {
      images: ["me1.png", "me2.png"],
      image: "me1.png"
    };
  },
  methods: {
    image1() {
      this.image = this.images[0];
    },
    image2() {
      this.image = this.images[1];
    }
  }
};
</script>
<style scoped>
a {
  color: black;
}
.successful-server-response-wrapper {
  display: flex;
  justify-content: center;
  align-content: center;
}

.successful-server-response {
  text-align: center;
  max-width: 500px;
  font-size: 36px;
  background-color: #5cb85c;
  color: #f1f1f1;
  padding: 20px;
  border-radius: 3px;
}
</style>