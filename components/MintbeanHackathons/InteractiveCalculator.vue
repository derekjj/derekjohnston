<template lang="pug">
  .container
    .row
      .col-12
        h2 Tip Calculator

    b-form
      .row
        .col
          b-form-group(
            id="input-billAmount"
            label="Bill Amount:"
            label-for="billAmount"
            description="Enter your bill amount")
            b-form-input(
              id="billAmount"
              v-model="form.billAmount"
              type="number"
              required
              placeholder="0.00")
      .row
        .col-12
          b-form-group(label="Tip")
            b-form-radio(v-model="form.tipStyle" name="some-radios" value="percent" selected) %
            b-form-radio(v-model="form.tipStyle" name="some-radios" value="flat") Flat

      .row
        .col-12
          b-form-group(
            id="input-tip"
            label="Tip:"
            label-for="tip"
            :description="'Enter your ' + form.tipStyle + ' tip'")
            b-form-input(
              id="tip"
              v-model="form.tip"
              type="number"
              required
              placeholder="0.00")
    .row.pt-5(v-show="grandTotal > 0 && isFinite(grandTotal)")
      .col-12
        .row.pb-5
          .col-2
          .col-3.bg-secondary.text-light
            | Bill Amount
          .col-2
          .col-3.bg-dark.text-light
            | Tip Amount
          .col-2
        .row.pb-5
          div.bg-secondary.text-light(
            :style="{width: (form.billAmount/grandTotal*100) + '%'}")
            | ${{parseFloat(form.billAmount).toFixed(2)}}
            br
            | {{(form.billAmount/grandTotal*100).toFixed(2)}}%
          div.bg-dark.text-light(
            :style="{width: (tipAmount/grandTotal*100)+ '%'}")
            | ${{parseFloat(tipAmount).toFixed(2)}}
            br
            | {{(tipAmount/grandTotal*100).toFixed(2)}}%
        .row
          .col-12 Grand total: ${{parseFloat(grandTotal).toFixed(2)}}
</template>
<script>
export default {
  data() {
    return {
      form: {
        billAmount: 0,
        tipStyle: "percent",
        tip: 0
      },
    };
  },
  computed: {
    grandTotal() {
      return +this.form.billAmount + +this.tipAmount
    },
    tipAmount() {
      if(this.form.tipStyle === "percent"){
        return this.form.billAmount * (this.form.tip/100)
      } else {
        return this.form.tip
      }
    }
  }
};
</script>