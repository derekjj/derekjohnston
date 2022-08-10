<template>
  <b-container fluid class="mt-5">
    <b-row class="text-center bg-success">
      <h1>Vaccine Time Slot Helper</h1>
    </b-row>
    <b-row class="text-center">
      <span>
        *information displayed here isn't locally controlled by this site*
      </span>
    </b-row>
    <b-row class="text-center">
      <span class="m-2">
        *this is like you clicking every calendar date at once*
      </span>
    </b-row>
    <b-row class="text-center pb-3">
      <span>
        *data is to be used for reference only, not responible for incorrect
        information *
      </span>
    </b-row>
    <b-row>
      <b-col
        cols="12"
        md="6"
        lg="4"
        v-for="(location, i) in locations"
        :key="i + 'locations'"
      >
        <b-row>
          <b-col cols="1">
            <b-form-checkbox :value="location" v-model="searching" />
          </b-col>
          <b-col cols="11" class="text-left">{{ location.name }}</b-col>
        </b-row>
      </b-col>
    </b-row>
    <b-row cols="6" v-for="(search, i) in searching" :key="i + 'search'">
      <b-col cols="12" class="p-3">
        <b-row class="text-center">
          <h2>{{ search.name }}</h2>
          <span class="m-2">
            * If failing to load you must be activily signed in *
          </span>
          <span class="m-2">
            <b-button
              :href="`https://durhamregion.vertoengage.com/engage/api/api/cac-open-clinic/v1/slots/availability?day=${date.getFullYear()}-${date.getMonth()}-${date.getDate()}T00:00:00.000-05:00&location_id=CGV&slot_type=PATIENT&key=durham-booking`"
              onclick="window.open(this.href,'_self');window.open('#','_blank');"
            >
              check activity
            </b-button>
          </span>
        </b-row>
        <b-row class="text-center">
          <span>
            <b-button
              class="m-4"
              href="https://www.durhamvaccinebooking.ca/"
              target="_blank"
            >
              www.durhamvaccinebooking.ca
            </b-button>
            <b-button
              class="m-4"
              href="https://durhamregion.vertoengage.com/engage/generic-open-clinic?key=durham-booking"
              target="_blank"
            >
              (skipping right to the booking page)
            </b-button>
          </span>
        </b-row>
      </b-col>

      <b-col cols="12" v-if="slots.length < 1" class="p-3 text-center">
        <span>Loading...</span>
      </b-col>
      <b-col v-else cols="12" md="6" lg="4" v-for="(slot, i) in slots" :key="i">
        <b-row v-if="monthCheck(slot.month)" style="width: 100vw; left: 0;" class="p-5">
          <b-col>
            {{
              new Date(slot.year, slot.month, slot.day).toLocaleString(
                "en-US",
                {
                  month: "long",
                }
              )
            }}
          </b-col>
        </b-row>
        <b-row class="text-center" align-v="center">
          <b-col>
            <iframe
              :src="`https://durhamregion.vertoengage.com/engage/api/api/cac-open-clinic/v1/slots/availability?day=${
                slot.year
              }-${slot.month + 1}-${slot.day}T00:00:00.000-05:00&location_id=${
                search.code
              }&slot_type=PATIENT&key=durham-booking`"
              title="W3Schools Free Online Web Tutorials"
              id="iframe_id"
              height="40px"
              width="140px"
              scrolling="no"
            />
          </b-col>
          <b-col>
            {{
              new Date(slot.year, slot.month, slot.day).toLocaleDateString(
                "en-US"
              )
            }}</b-col
          >
        </b-row>
      </b-col>
    </b-row>
    <b-row class="text-center">
      <span>
        *This is just a tool I made for self use because I was sick of their bad
        site design*
      </span>
    </b-row>
  </b-container>
</template>

<script>
export default {
  layout: "demo",
  data() {
    return {
      date: new Date(),
      currentMonth: new Date().getMonth(),
      slots: [],
      locations: [
        { code: "CGV", name: "Bowmanville" },
        { code: "SAV", name: "Brock - Sunderland Town Hall" },
        { code: "WSV", name: "Whitby - 4160 Baldwin St. South Unit K7/8" },
        {
          code: "OSH",
          name: "Oshawa - 419 King St W. (Former Sears - North Side of Mall)",
        },
        { code: "PCV", name: "Pickering - 1899 Brock Rd Unit C3" },
        {
          code: "RAV",
          name: "Scugog Rotating Clinics - (See website for location)",
        },
        { code: "OOV", name: "Ajax Audley Recreation Centre" },
        { code: "UAV", name: "Uxbridge Sandford Community Ceneter" },
      ],
      searching: [],
    };
  },
  created() {
    //allowing for delay for othersites redirect
    setTimeout(() => this.loadData(), 5000);
  },
  methods: {
    monthCheck(slotMonth) {
      if (slotMonth != this.currentMonth) {
        this.currentMonth = slotMonth;
        return true;
      }
      return false;
    },
    daysInMonth(month, year) {
      return new Date(year, month + 1, 0).getDate(); //day zero gets the last day of the prevous month
    },
    loadData() {
      this.date = new Date();
      var month = this.date.getMonth();
      var year = this.date.getFullYear();
      // console.log("date", this.date);
      // console.log("getMonth", this.date.getMonth());
      // console.log("getDate", this.date.getDate());
      // console.log("daysInMonth", this.daysInMonth(month, year));
      //this month
      for (
        var i = this.date.getDate();
        i <= this.daysInMonth(month, year);
        i++
      ) {
        this.slots.push({ day: i, month: month, year: year }); //They aren't using zero index
        console.log("i", i);
        console.log(
          `this.daysInMonth(${month}, ${year})`,
          this.daysInMonth(month, year)
        );
      }

      // next month
      if (month === 11) {
        year++;
        month = 0;
      }

      month++;
      for (var x = 1; x <= this.daysInMonth(month, year); x++) {
        this.slots.push({ day: x, month: month, year: year });
        console.log("x", x);
        console.log(
          `this.daysInMonth(${month}, ${year})`,
          this.daysInMonth(month, year)
        );
      }

      //next month
      if (month === 11) {
        year++;
        month = 0;
      }

      month++;
      for (var x = 1; x <= this.daysInMonth(month, year); x++) {
        this.slots.push({ day: x, month: month, year: year });
      }
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
iframe {
  overflow: hidden;
}
span {
  height: 100%;
}
</style>
